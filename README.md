php occ app:install notify_push
php occ notify_push:setup https://nextcloud.hartig.es/push
php occ notify_push:metrics
php occ notify_push:self-test

php occ background:cron
php occ config:system:set maintenance_window_start --type=integer --value=1
php occ config:system:set default_phone_region --value='DE'

php occ config:system:get enabledPreviewProviders

php occ config:system:set enabledPreviewProviders 0 --value 'OC\Preview\TXT'
php occ config:system:set enabledPreviewProviders 1 --value 'OC\Preview\MarkDown'
php occ config:system:set enabledPreviewProviders 2 --value 'OC\Preview\MP3'
php occ config:system:set enabledPreviewProviders 3 --value 'OC\Preview\OpenDocument'
php occ config:system:set enabledPreviewProviders 4 --value 'OC\Preview\Krita'
php occ config:system:set enabledPreviewProviders 5 --value 'OC\Preview\Imaginary'
php occ config:system:set enabledPreviewProviders 6 --value 'OC\Preview\ImaginaryPDF'
php occ config:system:set preview_imaginary_url --value 'http://imaginary:9000'
php occ config:system:set preview_concurrency_all --value 12
php occ config:system:set preview_concurrency_new --value 8

php occ app:install user_oidc
php occ app:install groupfolders

php occ config:app:set richdocuments wopi_allowlist --value  '172.16.0.0/12 192.168.0.0/16 10.0.0.0/8 fc00::/7 fe80::/10 2001:db8::/32'