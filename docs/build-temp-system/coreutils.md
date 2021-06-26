<package-info :package="package" showsbu></package-info>

<script>
		new Vue({
		el: '#main',
		data: { package: {} },
		mounted: function () {
				this.getPackage('coreutils');
		},
		methods: {
			getPackage: function(name) {
					getPackage(name)
					.then(response => this.package = response);
			},
		}
  })
</script>

## Настройка

Запустите скрипт `configure`:

```bash
./configure --prefix=/usr                     \
            --host=$LIN_TGT                   \
            --build=$(build-aux/config.guess) \
            --enable-install-program=hostname \
            --enable-no-install-program=kill,uptime  \
            --disable-nls
```

### Значения параметров

` --enable-install-program=hostname` - Включает установку программы `hostname`, нужной некоторым пакетам.

`--enable-no-install-program=kill,uptime` - Программы `kill` и `uptime` предоставляются другими пакетами.

## Сборка

```bash
make
```

## Установка

```bash
make DESTDIR=$LIN install
```
