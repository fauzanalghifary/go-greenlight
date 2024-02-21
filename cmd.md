### PSQL

psql --dbname=greenlight --username=greenlight --host=localhost
psql -U quipperindonesia -d greenlight
SELECT current_user;

### Migration

migrate -path=./migrations -database=$GREENLIGHT_DB_DSN up
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN version
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN goto 1
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN down 1
migrate -path=./migrations -database=$GREENLIGHT_DB_DSN down

migrate -path=./migrations -database=$GREENLIGHT_DB_DSN force 1

migrate -source="s3://<bucket>/<path>" -database=$EXAMPLE_DSN up
migrate -source="github://owner/repo/path#ref" -database=$EXAMPLE_DSN up
migrate -source="github://user:personal-access-token@owner/repo/path#ref" -database=$EXAMPLE_DSN up