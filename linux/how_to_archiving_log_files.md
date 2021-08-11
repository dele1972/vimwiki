# Archiving Logfiles

## 1. Create a Folder-Structure with current date:

```shell
mkdir -p api-test--$(date +%Y-%m-%d)/{logs,hornet_api_tests/logs}
```

## 2. Move corresponding log files:

```shell
mv logs/* api-test--$(date +%Y-%m-%d)/logs
```

## 3. Create Archive and remove the temporary Folder-Structure:

```shell
tar -czvf api-test--$(date +%Y-%m-%d).tar.gz api-test--$(date +%Y-%m-%d) && rm -r api-test--$(date +%Y-%m-%d)
```

