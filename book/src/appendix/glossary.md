# Lampiran A: Glosarium

- Fast Path - Istilah yang digunakan untuk menggambarkan sebuah transaksi yang tidak melibatkan shared object,
  dan bisa dieksekusi tanpa perlu konsensus.
- Parallel Execution -istilah yang digunakan untuk menggambarkan kemampuan runtime Sui untuk mengeksekusi
  transaksi secara paralel, termasuk transaksi yang melibatkan shared objects.
- Internal Type - tipe yang didefinisikan di dalam modul. Ruang lingkup dari tipe ini tidak bisa diakses
  dari luar modul, dan, dalam kasus "key"-only abilities, tidak bisa digunakan dalam fungsi transfer `public_*`
  

## Abilities

- key - ability that allows the struct to be used as a key in the storage. On Sui, the key ability
  marks an object and requires the first field to be a `id: UID`.
- store - ability that allows the struct to be stored inside other objects. This ability relaxes
  restrictions applied to internal structs, allowing `public_*` transfer functions to accept them as
  arguments. It also enables the object to be stored as a dynamic field.
- copy - ability that allows the struct to be copied. On Sui, the `copy` ability conflicts with the
  `key` ability, and can not be used together with it.
- drop - ability that allows the struct to be ignored or discarded. On Sui, the `drop` ability
  cannot be used together with the `key` ability, as objects are not allowed to be ignored.
