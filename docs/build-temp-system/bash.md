<package-info :package="package" showsbu></package-info>

<script>
		new Vue({
		el: '#main',
		data: { package: {} },
		mounted: function () {
				this.getPackage('bash');
		},
		methods: {
			getPackage: function(name) {
					getPackage(name)
					.then(response => this.package = response);
			},
		}
  })
</script>

### Настройка

Запустите скрипт `configure`:

```bash
./configure --prefix=/usr                   \
            --build=$(support/config.guess) \
            --host=$LIN_TGT                 \
            --without-bash-malloc
```

#### Значения параметров

`--without-bash-malloc` - этот параметр отключает использование функции выделения памяти (malloc) Bash, которая вызывает ошибки сегментации. Отключив эту опцию, Bash будет использовать функции malloc из libc, которые более стабильны.

### Сборка

```bash
make
```

## Установка

```bash
make DESTDIR=$LIN install
```

Переместите `bash` в нужную директорию:

```bash
mv $LIN/usr/bin/bash $LIN/bin/bash
```

Сделайте символическую ссылку для программ, которые используют `sh` в качестве интерпретатора:

```bash
ln -sv bash $LIN/bin/sh
```
