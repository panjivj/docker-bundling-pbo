0. Rename folder src:
   mv src src_old

1. Kita build docker container terlebih dahulu jalankan:
   docker compose up -d --build

2. Cek nama project:
   docker ps

3. kemudian kita masuk ke container project:
   docker exec -it fill

4. Lanjut Create project
   composer create-project laravel/laravel .

5. Mulai buat filament
   composer require filament/filament:"^3.1" -W

   mv .env.example .env

   php artisan key:generate

   php artisan storage:link

   chmod 777 -R storage/\*

   php artisan migrate

php artisan filament:install --panel

php artisan make:filament-user

php artisan make:filament-resource User --generate

php artisan make:model Tag -m
php artisan make:model Category -m
php artisan make:model Product -m

buat relasi:
php artisan make:migration Product_tag

php artisan make:filament-resource Product --generate
php artisan artisan make:filament-relation-manager Product Tag

<!-- php artisan make:filament-resource Product --generate -->
