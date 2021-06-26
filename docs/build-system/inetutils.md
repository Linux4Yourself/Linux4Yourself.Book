<pkg :name="'inetutils'" instsize showsbu2></pkg>

## Настройка

<package-script :package="'inetutils'" :type="'configure'"></package-script>

### Значения параметров

`--disable-*` - Отключает установку программ, лучшие версии которых предоставляют другие пакеты.

## Сборка

<package-script :package="'inetutils'" :type="'build'"></package-script>

## Тестирование

<package-script :package="'inetutils'" :type="'test'"></package-script>

?> Тест `libls.sh` даёт сбой, когда система LX4 находится в среде chroot, а тест `ping-localhost.sh` не проходит, если в хост-системе нет поддержки IPv6.

## Установка

<package-script :package="'inetutils'" :type="'install'"></package-script>

## Установленные файлы

Программы: dnsdomainname, ftp, ifconfig, hostname, ping, ping6, talk, telnet, tftp и traceroute

<script>
	new Vue({ el: '#main' })
</script>
