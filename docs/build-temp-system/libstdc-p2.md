<package-info :package="package" showsbu></package-info>

<script>
		new Vue({
		el: '#main',
		data: { package: {} },
		mounted: function () {
				this.getPackage('gcc');
		},
		methods: {
			getPackage: function(name) {
					getPackage(name)
					.then(response => this.package = response);
			}
		}
  })
</script>

## Настройка

!> **Данный пакет входит в архив с исходниками GCC**

Создайте необходимую символическую ссылку:

```bash
ln -s gthr-posix.h libgcc/gthr-default.h
```

Создайте отдельную директорию для сборки:

```bash
mkdir -v build
cd       build
```

Запустите скрипт `configure` 

```bash
../libstdc++-v3/configure            \
    CXXFLAGS="-O2 -s -D_GNU_SOURCE"  \
    --prefix=/usr                    \
    --disable-nls                    \
    --host=$(uname -m)-lin-linux-gnu \
    --disable-libstdcxx-pch --disable-multilib
```

### Для multilib

Замените ``--disable-multilib`` на ``--enable-multilib``.

### Объяснение параметров configure

`--disable-libstdcxx-pch` - Отключает установку предварительно скомпилированных заголовков, не нужных на данном этапе

`--host=$(uname -m)-lin-linux-gnu` - Libstdc++ должна быть собрана с такими же параметрами, что и GCC

## Сборка

```bash
make
```

## Установка

Для установки этого пакета выполните

```bash
make install
```
