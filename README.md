# Usando Entwine

Conjuntos de instruções, testes e exemplos de como utilizar nuvem de pontos LiDAR em formato Entwine (EPT)

## Formato EPT

O [Entwine Point Tile](https://entwine.io/) (EPT) é um formato de armazenamento simples e flexível baseado em octree para dados de nuvem de pontos.
A grande vantagem desse formato é sua flexibilidade, pois é capaz de trabalhar com escalas que vão, por exemplo, desde os limites do município de São Paulo até o lote individual. Isso permite, entre tantas coisas poder visuazlizar pela web sem precisar baixar uma quantidade grande de dados.
Além disso o formato permite uso de ferramentas de análise diretamente que é o que vamos tentar demonstrar por aqui nesse repositório.

## PDAL

Vamos utilizar a biblioteca e aplicação Open Source [PDAL](https://pdal.io) que pode ser obtido e instalado sem custo e nem tampoco esforço.

## PDAL Pipelines

O PDAL permite compor operações em nuvens de pontos em pipelines. Esses pipelines podem ser gravados em uma formato JSON declarativo ou construídos usando a API disponível.
Para a finalidade desse repostiório vamos criar diversos Pipelines e decrever seu funcionamento abaixo.

## Hello World EPT

Primeiro vamos executar um simples pipeline para fazer o download de uma porção da Nuvem de Pontos

`pdal pipeline .\pipelines\bouding_box.json`

Podemos optar por fazer o download de uma densidade de pontos mais baixa, como por exmeplo com resolução de 1 ponto por metro quadrado

`pdal pipeline .\pipelines\bouding_box_1_metro.json`

Também podemos salvar em formatos distintos como no caso o PLY para visualizar no [Blender 3D](https://www.blender.org/)

`pdal pipeline .\pipelines\bouding_box_to_ply.json`

E podemos ainda gerar um mesh para visualização

`pdal pipeline .\pipelines\bouding_box_to_ply_mesh.json`

E podemos gerar um mesh com o algorítimo Greedy

`pdal pipeline .\pipelines\bouding_box_to_ply_mesh_greedy.json`

E podemos gerar um mesh com o algorítimo Poisson

`pdal pipeline .\pipelines\bouding_box_to_ply_poisson.json`