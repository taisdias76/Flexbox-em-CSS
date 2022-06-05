# Posicionando elementos com Flexbox em CSS - DIO 

## Introdução ao Flexbox
O Flexbox foi projetado como um modelo de layout unidimensional e como um método que pode oferecer distribuição de espaço entre itens em uma interface e recursos de alinhamento.

- Flex Container
  - É a tag que envolve os itens, será nela que iremos aplicar a propriedade "display: flex";
  - Transforma todos os seus itens filhos em flex itens;
  - Essa propriedade de display pode ser feita em qualquer tipo de tag (div, span, h1...);
  - Propriedades relacionadas:
    * display: inicializador do container
    * flex-direction: faz o direcionamento dos itens
    * flex-wrap: define se os itens flexíveis são forçados a ficarem na mesma linha ou se podem ser quebradas em várias linhas
    * flex-flow: junção das propriedades flex-direction e flex-wrap
    * justify-content: alinha os itens do container de acordo com a sua direção
    * align-items: alinha os itens de acordo com o seu eixo do container 
    * align-content: alinha as linhas do container

- Flex Item
  - São os elementos filhos diretos do Flex Container;
  - Também podem se tornar Flex Container
  - Propriedades relacionadas:
    * flex-grow: define o fator de crescimento e aceita valores sem unidades de medida e os usa como proporção
    * flex-basis: define o tamanho inicial do item antes que o espaço restante seja ditribuído
    * flex-shrink: define a capacidade de redução
    * flex: abreviação para as propriedade basis, shrink e o grow
    * order: relacionado a ordem de distribuição e listagem dos itens
    * align-self: define o alinhamento de um item específico do container

## Fundamentos - Flex Container
- Display: flex
  - Torna a tag um elemento do tipo flex container, e assim automaticamente todos os seus filhos diretos desta tag, tornam-se flex itens 
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032649-dbf7d89b-396a-4afc-bc75-4c911b58b766.PNG" /> 
    </p>
    
    
- Flex-direction
  - Estabelece o eixo principal do container, definindo assim a direção que os flex itens são colocados no flex container;
  - row (padrão): à direção do texto, esquerda para direita;
  - row-reverse: sentido oposto à direção do texto;
  - column: ordenação de cima para baixo, em coluna única;
  - column-reverse: ordenação inversa, de baixo para cima.
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032712-684f8837-13b0-44ec-b35b-4a0b1aae0f95.PNG" /> 
    </p>
    

- Flex-wrap
  - É a propriedade que define se os itens devem ou não quebrar a linha;
  - Por padrão eles não quebram linhas, isso faz com que os itens sejam compactados além do limite do conteúdo;
  - nowrap: é o padrão, não permite a quebra de linha;
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032769-6215b936-8cd7-4467-9c72-3b29c59c1246.PNG" /> 
    </p>

  - wrap: permite a quebra de linha assim que um dos flex itens não puder mais ser compactado;
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032783-34835141-8d1e-41b6-8316-0b9f3e4db50e.PNG" /> 
    </p>

  - wrap-reverse: permite a quebra de linh assim que um dos flex itens não puder mais ser compactado, porém na direção contrária da linha - acima.
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032798-ca2a370f-886f-4467-97c8-03d0eccae1cd.PNG" /> 
    </p>
    
    
- Flex-flow
  - É o atalho para as propriedade flex-direction e flex-wrap;
  - Porém seu uso não é tão comum, visto que, quando mudamos o flex-direction para colum, mantemos o padrão do flex-wrap que é nowraps.

    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032816-39847f3e-9021-42cc-9e6e-b4e35bc915d7.PNG" /> 
    </p>


- Justify-content
  - Essa propriedade vai se encarregar de alinhar os itens dentro do container de acordo com a direção pretendida e tratar da distribuição de espaçamento entre eles;
  - Variações:
    * flex-start: início do container;
    * flex-end: final do container;
    * center: ao centro do container;
    * space-between: cria um espaçamento igual entre os elementos - Distribui os itens uniformemente, de modo que o primeiro está no inicio do container enquanto o último está ao final;
    * space-around: os espaçamentos do meio são duas vezes maiores que o inicial e o final.
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032830-d735298e-2e80-4a67-9ae2-6254170cde17.PNG" /> 
    </p>

- Align-items
  - Trata do alinhamento dos flex itens de acordo com o eixo do container;
  - O alinhamento é diferente para quando os itens estão em colunas ou linhas;
  - Permite o alinhamento central no eixo vertical;
  - Tipos de alinhamento:
    * center: alinhamento dos itens ao centro;
    * stretch: padrão, e os flex itens crescem igualmente - estica os itens de modo que preencham o container
    * flex-start: alinhamento dos itens no início
    * flex-end: alinhamento dos itens no final
    * baseline: alinhamento de acordo com a linha base da tipografia dos itens
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032858-4ba7fc84-2806-4415-8ff0-f6379040d051.PNG" /> 
    </p>


- Align-content
  - É a propriedade responsável por tratar o alinhamento das linhas do container em relação ao eixo vertical do container;
  - Precisamos que:
    * O container utilize quebra de linhas;
    * A altura do container seja maior que a soma das linhas dos itens;
  - Tipos de alinhamento:
    * Center: alinhamento dos itens ao centro;
    * Stretch: é o padrão e os flex itens crescem igualmente;
    * Flex-start: alinhamento dos itens no início;
    * Flex-end: alinhamento dos itens no final
    * Space-between: cria um espaçamento igual entre os elementos
    * Space-around: os espaçamentos do meio são duas vezes maiores que o inicial e o final


## Fundamentos - Flex Item

- Flex-grow
  - Define a proporcionalidade de crescimentos dos itens, respeitando o tamanho de seus conteúdos internos;
  - Obs.: não irá funcionar caso tenhamos adicionado justify-content ao nosso flex container;
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032878-43dddbcb-d966-4151-8a2d-93bd46359082.PNG" /> 
    </p>


- Flex-basis
  - É a propriedade que estabelece o tamanho inicial do item antes das distribuições de espaço restante dentro dele, usando como base o conteúdo interno disposto;
  - Valores possíveis:
    * auto: caso o item não tenha tamanho, este será proporcional ao conteúdo do item;
    * px, %, em, ..: são valores exatos previamente definidos;
    * 0 (zero): terá relação com a definição do flex-grow
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032891-210a3325-bfd8-4749-9c59-5561f7e0cb92.PNG" /> 
    </p>


- Flex-shrink
  - É a propriedade que estabelece a capacidade de redução ou compressão do tamanho de um item;
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032901-a5d5fc3a-0daa-4c2d-bb6c-148b68289d1e.PNG" /> 
    </p>


- Flex
  - Esta propriedade é um atalho ou abreviação de escrita para as propriedades: grow, shrink e basis
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032928-e0b6af69-a601-416b-9305-c2be92bb6191.PNG" /> 
    </p>


- Order
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032943-829cc4c8-64f3-4145-b42d-dcb55ca9bfda.PNG" /> 
    </p>


- Align-self
  - É a propriedade que estabelece o alinhamento de modo individual sobre um determinado item;
  - Valores possíveis:
    * auto: valor padrão, irá respeitar a definição de align-items dos container;
    * flex-start: ao início do container;
    * flex-end: ao final do container;
      center: relaivo ao centro de acordo com o eixo;
    * stretch: ocupa todo o espaço relativo;
    * baseline: utiliza a linha base da tipografia; 
    <p align="center">
      <img src="https://user-images.githubusercontent.com/82185476/172032952-c125125b-37c0-43b9-8c6b-342e58b3f362.PNG" /> 
    </p>




### Referências
- <a href="https://web.dio.me/course/posicionando-elementos-com-flexbox-em-css/learning/ce6a5dde-a4be-4d48-9470-7b1dbe227b73?back=/track/santander-bootcamp-fullstack-developer&tab=undefined&moduleId=undefined">DIO</a>

- <a href="https://pingback.com/gabcodes/css-flexbox-como-posicionar-elementos-na-tela">CSS Flexbox</a>

- <a href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/align-items">mdn</a>
