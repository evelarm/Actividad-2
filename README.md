struct Articulo {
  var nom: String
  var cant: Int
}

func registroArticulo() -> Articulo {
  print("~~~~~~ Registrar Articulo ~~~~~~~")
  print("Ingresa el nombre del articulo")
  let nom = readLine()!
  print("Ingresa la cantidad")
  let cant = Int(readLine()!)!
  return Articulo(nom: nom, cant: cant)
}

func mostrarlistado(articulos:[Articulo]){
  print("~~~~~~ Listado de articulos ~~~~~~")
  for(indice, articulo) in articulos.enumerated(){
    print("Articulo \(indice+1): \(articulo.nom)")
    print("Cantidad: \(articulo.cant)")
  }
}

func consultadeArticulo(articulos:[Articulo]){
  print("~~~~~~~~~~~ Consulta ~~~~~~~~~~~~")
  print("Nombre del Articulo a Consultar")
  let nom = readLine()!
  for(indice, articulo) in articulos.enumerated(){
    if articulo.nom == nom {
    print("Articulo consultado \(indice+1): \(articulo.nom)")
    print("Cantidad del articulo consultado: \(articulo.cant)")
    break
  }
    
  }
  
}


var articulos:[Articulo]=[]
var opc = 0
repeat { 
  print("°°°°°°°°°°° MENÚ °°°°°°°°°°°")
  print("       1. Registro")
  print("       2. Listado")
  print("       3. Consulta")
  print("       4. Salir")
  opc = Int(readLine()!)!
  switch opc{
    case 1:
      let newArticulo = registroArticulo()
      articulos.append(newArticulo)
      print("/// Articulo Registrado Exitosamente ///")
    case 2:
      mostrarlistado(articulos:articulos)
      print("---------------------------------")
    case 3:
      consultadeArticulo(articulos:articulos)
      print("---------------------------------")
    case 4:
      print("Salir")
    default:
      print("Opción invalida")
  }      
}  while opc != 4
