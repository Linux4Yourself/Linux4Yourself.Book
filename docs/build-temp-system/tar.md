<package-info :package="package" showsbu></package-info>

<script>
                new Vue({
                el: '#main',
                data: { package: {} },
                mounted: function () {
                                this.getPackage('tar');
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

```bash
./configure --prefix=/usr                     \
            --host=$LIN_TGT                   \
            --build=$(build-aux/config.guess)  --disable-nls  --disable-acl
```

## Сборка

```bash
make
```

## Установка

```bash
make DESTDIR=$LIN install
```
