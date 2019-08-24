# Practica terminada...

<a href="https://ibb.co/KDB11Fx"><img src="https://i.ibb.co/FXcPPg4/crud.png" alt="crud" border="0"></a>
<br>

> - [x] Agregado el metodo `edit` al controlador `NotaController`.

```
public function edit($id)
    {
        $nota = App\Nota::findOrFail($id);
        return view('notas.editar', compact('nota'));
    }

```

> - [x] Agregado el metodo `update` al controlador `NotaController`.

```
public function update(Request $request, $id)
    {
        $notaUpdate = App\Nota::findOrFail($id);
        $notaUpdate->nombre = $request->nombre;
        $notaUpdate->descripcion = $request->descripcion;

        $notaUpdate->save();

        return back()->with('mensaje', 'Nota Editada Felicidades!!!');

    }
```

> - [x] Agregado el metodo `destroy` al controlador `NotaController`.

```
public function destroy($id)
    {
        $notaDestroy = App\Nota::findOrFail($id);
        $notaDestroy->delete();

        return back()->with('mensaje', 'Nota Eliminada');
    }
```


