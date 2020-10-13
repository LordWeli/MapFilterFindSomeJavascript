# MapFilterFindSome()

## Estudo dos métodos map(), filter(), find() e some() do Javascript.

Conteúdo
=================
- [Sobre](#sobre)
- [Estrutura](#estrutura)
- [Uso do map() para mudança de dado](#uso-do-map)
  - [Mudança na Estrutura com o map()](#mudança-na-estrutura-map)
- [Uso do filter()](#uso-do-filter)
  - [Retorno do filter()](#retorno-do-filter)
- [Uso do find()](#uso-do-find)
  - [Retorno do find()](#retorno-do-find)
- [Uso do some()](#uso-do-some)
- [Uso do filter() e map() para encontrar um padrão e fazer mudança de dado](#uso-do-filter-e-map)
  - [Mudança na Estrutura com o filter() e map()](#mudança-na-estrutura_filter_map)
- [Licença](#licenca)

## <a name="sobre"></a> Sobre
  Uso de chamadas de métodos Javascript para manipulação de objetos. Utilização estrutura baseada em animais com os métodos map(), filter() e find() para mudança de campos e retorno dos dados do objeto. Baseado no artigo [Entendendo map, filter, some, find e reduce do JavaScript com Pokemons.](https://medium.com/@mathiasghenoazzolini/entendendo-map-filter-some-find-e-reduce-do-javascript-com-pokemons-e4884551817b).


## <a name="estrutura"></a> Estrutura
```javascript
  var animais = [{
    id: 1,
    nome: 'Capivara',
    tipo: 'Mamífero roedor',
    nome_tipo: '',
    primeiro_tipo: ''
  },{
    id: 2,
    nome: 'Onça-pintada',
    tipo: 'Mamífero carnívoro',
    nome_tipo: '',
    primeiro_tipo: ''
  },{
    id: 3,
    nome: 'Jacaré',
    tipo: 'Carnívoro voraz',
    nome_tipo: '',
    primeiro_tipo: ''
  }];
```

## <a name="uso-do-map"></a> Uso do map() para mudança de dado
```javascript
  var map_resultado = animais.map(animal => {
    return animal.nome_tipo = animal.nome + ' - ' + animal.tipo;
  });
```

#### <a name="mudança-na-estrutura-map"></a> Mudança na Estrutura

```javascript
  [{
    id: 1,
    nome: 'Capivara',
    tipo: 'Mamífero roedor',
    nome_tipo: 'Capivara - Mamífero roedor',
    primeiro_tipo: ''
  },{
    id: 2,
    nome: 'Onça-pintada',
    tipo: 'Mamífero carnívoro',
    nome_tipo: 'Onça-pintada - Mamífero carnívoro',
    primeiro_tipo: ''
  },{
    id: 3,
    nome: 'Jacaré',
    tipo: 'Carnívoro voraz',
    nome_tipo: 'Jacaré - Carnívoro voraz',
    primeiro_tipo: ''
  }];
```

## <a name="uso-do-filter"></a> Uso do filter()
```javascript
  var filter_resultado = animais.filter(animal => {
    return animal.tipo.toLowerCase().includes('carnívoro');
  });
```

#### <a name="retorno-do-filter"></a> Retorno do filter()
```javascript
  [{
    id: 2,
    nome: 'Onça-pintada',
    tipo: 'Mamífero carnívoro',
    nome_tipo: 'Onça-pintada - Mamífero carnívoro',
    primeiro_tipo: ''
  },{
    id: 3,
    nome: 'Jacaré',
    tipo: 'Carnívoro voraz',
    nome_tipo: 'Jacaré - Carnívoro voraz',
      primeiro_tipo: ''
  }];
```

## <a name="uso-do-find"></a> Uso do find()
```javascript
  var find_resultado = animais.find(animal => animal.id === 2);

  // ou

  var find_resultado = animais.find(animal => {
    return animal.id === 2;
  });
```

#### <a name="retorno-do-find"></a> Retorno do find()
```javascript
  {
    id: 2,
    nome: "Onça-pintada",
    tipo: "Mamífero carnívoro",
    nome_tipo: "Onça-pintada - Mamífero carnívoro",
    primeiro_tipo: ""
  }
```

## <a name="uso-do-some"></a> Uso do some()
- Busca de padrão existente:
```javascript
  var some_resultado = animais.some(animal => animal.nome === 'Jacaré');

  true // Retorna true se o padrão existir
```

- Busca de padrão não existente:
```javascript
  var some_resultado = animais.some(animal => animal.nome === 'Macaco');

  false // Retorna false se o padrão não existir
```

## <a name="uso_do_filter_e_map"></a> Uso do filter() e map() para encontrar um padrão e fazer mudança de dado
```javascript
  var parametro = 'mamífero'; // Uso de variável para guardar o valor 'mamífero'.
  var filter_map_result = animais.filter(animal => {
    return animal.tipo.toLowerCase().includes(parametro);
  }).map(animal => {
    return animal.primeiro_tipo = parametro.charAt(0).toUpperCase() + parametro.slice(1); // Uso de capitalize para o nome do tipo.
  });
```

#### <a name="mudança-na-estrutura_filter_map"></a> Mudança na Estrutura com o filter() e map()
```javascript
  [{
    id: 1,
    nome: 'Capivara',
    tipo: 'Mamífero roedor',
    nome_tipo: 'Capivara - Mamífero roedor',
    primeiro_tipo: 'Mamífero'
  },{
    id: 2,
    nome: 'Onça-pintada',
    tipo: 'Mamífero carnívoro',
    nome_tipo: 'Onça-pintada - Mamífero carnívoro',
    primeiro_tipo: 'Mamífero'
  },{
    id: 3,
    nome: 'Jacaré',
    tipo: 'Carnívoro voraz',
    nome_tipo: 'Jacaré - Carnívoro voraz',
    primeiro_tipo: ''
  }];
```

## <a name="licenca"></a> Licença
  MapFilterFind is released under the [MIT License](https://opensource.org/licenses/MIT).