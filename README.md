# scene2d

## Scene2d UI Libgdx

* Informasi : Kode program ini adalah implementasi Scene2d pada libgdx
* Link youtube : 
* Versi : 0.1

## Penjelasan
Scene2d digunakan untuk ui pada game libgdx, memungkinkan kita untuk membuat ui button [libgdx scene2d](https://libgdx.com/wiki/graphics/2d/scene2d/scene2d).

Pembuatan scene2d ui dapat dilakukan dengan cara manual atau menggunakan skin composer, untuk membuat asset lebih mudah. Ini terlihat pada assets project terdapat beberapa file, yang akan menyimpan data style daripada skin scene2d. 

`Skin textButtonSkin = new Skin(Gdx.files.internal("skins.json"));`

load skins file dari folder assets

```
        // inisialisasi textButton dengan string text (play) dan pemberian skins ke textButton, dengan style default
        textButton = new TextButton("play",textButtonSkin);

        // pemberian aksi ketika textButton di click
        textButton.addListener(new ClickListener(){
            @Override
            public void clicked(InputEvent event, float x, float y) {
                Gdx.app.debug("clicked","text button play");
            }
        });
```

Penggunaan table untuk memposisikan scene2d ui, agar kita dapat mudah mensejajarkan row atau column dengan table
```
Table table = new Table();

table.add(textButton);
// mode debug table
table.debugTable();
// pembuatan table seukuran dari layar window
table.setFillParent(true);
```

```
// inisialisasi stage
stage = new Stage(viewport);
stage.addActor(table);

// agar apapun ui yang ada pada stage dapat berinteraksi dengan input
Gdx.input.setInputProcessor(stage);
```

Urutan scene2d
1. Stage : kontainer yang menyimpan banyak aktor
2. Actor (button, checkbox, table, etc) : ui yang ada pada stage 
