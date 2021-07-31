<pkg :name="'zstd'" instsize showsbu2></pkg>

## Сборка

<package-script :package="'zstd'" :type="'build'"></package-script>

## Тестирование

<package-script :package="'zstd'" :type="'test'"></package-script>

## Установка

<package-script :package="'zstd'" :type="'install'"></package-script>

## Для multilib

### Очистка

<package-script :package="'zstd'" :type="'multi_prepare'"></package-script>

### Сборка

<package-script :package="'zstd'" :type="'multi_build'"></package-script>

### Установка

<package-script :package="'zstd'" :type="'multi_install'"></package-script>

## Установленные файлы

Программы: zstd, zstdcat (link to zstd), zstdgrep, zstdless, zstdmt (ссылка на zstd), and unzstd (ссылка на zstd)

Библиотеки: libzstd.so

### Краткое описание

`zstd` - Сжимает и распаковывает файлы с помощью алгоритма ZSTD

`libzstd` - библиотека для формата сжатия ZSTD

<script>
	new Vue({ el: '#main' })
</script>
