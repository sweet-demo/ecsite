# Supervisor設定

このディレクトリには、PHPコンテナ内でsupervisorを使用して複数のプロセスを管理するための設定ファイルが含まれています。

## 設定内容

### supervisord.conf
- **php-fpm**: PHP-FPMプロセスの管理
- **laravel-queue**: Laravel Queue Workerの管理
- **laravel-scheduler**: Laravel Schedulerの管理

```bash
# supervisorのステータス
docker compose exec php-fpm supervisorctl status

# supervisorのメインログ
docker compose exec php-fpm tail -f /var/log/supervisor/supervisord.log

# PHP-FPMのログ
docker compose exec php-fpm tail -f /var/log/supervisor/php-fpm.log

# Queue Workerのログ
docker compose exec php-fpm tail -f storage/logs/laravel-worker.log

# Schedulerのログ
docker compose exec php-fpm tail -f storage/logs/scheduler.log
```
