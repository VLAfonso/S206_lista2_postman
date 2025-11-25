# Lista2 - Teste de API com Postman
Repositório destinado à Lista de Exercício 2 - Teste de API com Postman - da disciplina S206 - Qualidade de Software.
O objetivo principal é o desenvolvimento de testes de API para [The Rick and Morty API](https://rickandmortyapi.com/).  
<img width="360" height="110" alt="image" src="https://github.com/user-attachments/assets/6b1e06dd-c414-4ca8-8fb3-1b939b785f21" />



## :pencil: Descrição
[The Rick and Morty API](https://rickandmortyapi.com/) é uma API baseada na série de televisão Rick and Morty que possui informações de centenas de personagens, imagens, localizações e episódios. Está repleta de informações canônicas, conforme visto na série.

Para a Questão 1 da Lista de Exercícios 2, foram desenvolvidos 7 cenários de testes de API, realizando requisições GET de personagens, localizações e episódios. Para a Questão 2, foram respondidas questões teóricas no tópico Análise teórica dos testes.

## :gear: Execução
1. Clonar o repositório
```bash
git clone https://github.com/VLAfonso/S206_lista2_Postman.git
cd S206_lista2_Postman
```
2. Instalar as dependências
```bash
npm install
```

3. Executar os testes
```bash
newman run Lista2-RickAndMorty.postman_collection.json -e Lista2-RickAndMorty.postman_environment.json -r htmlextra
```

4. Acessar relatório de testes  
O relatório é gerado automaticamente após a execução de testes e pode ser encontrado na pasta [`newman`](./newman).

> :pushpin: **Notas:** É necessário ter o [Node.js](https://nodejs.org/) instalado (versão 18 ou superior) e o npm configurado corretamente no sistema.

## :white_check_mark: Testes de API
Os testes de API foram divididos em 3 suítes de teste:
### Testes de localização de personagem:
| # | Cenário de Teste | Tipo | Descrição |
|----|------|---------|-----------|
| 1 | **Localiza personagem com sucesso** | Positivo | Localiza o personagem "Cool Rick" de forma válida. Verifica se o Status Code é 200 e se possui o nome do personagem no body da resposta. |
| 2 | **Não localiza personagem (Não existe)** | Negativo | Tenta localizar um personagem inexistente (1001). Verifica se o Status Code é 404 e se possui o erro "Character not found" no body da resposta. |
| 3 | **Endpoint falho localiza personagem** | Negativo | Tenta localizar o personagem "Cool Rick" com um endpoint falho (characte ao invés de character). Verifica se o Status Code é 404 e se possui o erro "There is nothing here." no body da resposta. |

### Testes de localização de localização:
| # | Cenário de Teste | Tipo | Descrição |
|----|------|---------|-----------|
| 1 | **Localiza localização com sucesso** | Positivo | Localiza a localização "Krootabulon" de forma válida. Verifica se o Status Code é 200 e se possui o nome da localização no body da resposta. |
| 2 | **Não localiza localização (Não existe)** | Negativo | Tenta localizar uma localização inexistente (451). Verifica se o Status Code é 404 e se possui o erro "Location not found" no body da resposta. |

### Testes de localização de episódio:
| # | Cenário de Teste | Tipo | Descrição |
|----|------|---------|-----------|
| 1 | **Localiza episódio com sucesso** | Positivo | Localiza o episódio "A Rickle in Time" de forma válida. Verifica se o Status Code é 200 e se possui o nome do episódio no body da resposta. |
| 2 | **Não localiza episódio (Não existe)** | Negativo | Tenta localizar um episódio inexistente (401). Verifica se o Status Code é 404 e se possui o erro "Episode not found" no body da resposta. |

Dessa forma, foram desenvolvidos 7 cenários de teste, sendo 3 positivos e 4 negativos.

### Relatório de testes
O relatório de testes é gerado em formato HTML pelo Newman e está presente na pasta [`newman`](./newman). Seu resultado pode ser visto a seguir:
<img width="1391" height="904" alt="image" src="https://github.com/user-attachments/assets/6a34a2da-01b8-4655-864b-acafdd586471" />
<img width="1391" height="500" alt="image" src="https://github.com/user-attachments/assets/072e9904-2812-42a4-b7df-b2827497db3d" />

## :blue_book: Análise teórica dos testes
1. Quantas suítes de testes você desenvolveu?  
Foram desenvolvidas 3 suítes de testes, sendo elas: Testes de localização de personagem, Testes de localização de localização e Testes de localização de episódio. Cada suíte possui seus respectivos cenários de teste e foram divididas por meio de pastas na Collection do Postman e baseadas no tipo de informação a ser requisitada.

2. Os testes desenvolvidos são manuais ou automatizados?  
Os testes desenvolvidos são automatizados, pois são códigos que verificam determinados cenários de testes e são executados de forma automatizada pelo Newman. 

3. Onde os testes se localizam na pirâmide apresentada?  
Os testes se localizam no meio da pirâmide, pois os testes de API são testes de integração.

4. Os testes desenvolvidos são funcionais ou não-funcionais?  
Os testes desenvolvidos são funcionais, pois verificam se o sistema faz o que se espera. Para serem não-funcionais, teriam que validar requisitos não funcionais, como desempenho e usabilidade, o que não ocorre nesse caso.

5. Alguns dos testes desenvolvidos são testes Fim-a-Fim (End-To-End)?  
Nenhum dos testes desenvolvidos são testes Fim-a-Fim, pois nenhum deles verifica o fluxo completo do software, apenas se uma requisição é feita e possui o retorno esperado.

6. O que se deve fazer para que os testes desenvolvidos funcionem em modo regressão?  
Para que os testes desenvolvidos funcionem em modo regressão, deve-se executar automaticamente todas as suítes de testes desenvolvidas sempre que houver qualquer alteração no software para a identicifação de possíveis erros que causem a regressão do código.

## :hammer_and_wrench: Tecnologias e Ferramentas Utilizadas
- Linguagem de Programação: **JavaScript**
- Criação de Testes: **Postman**
- Relatórios de Teste: **Newman** e **htmlextra**
- Ambiente de Execução: **Node.js**

## :busts_in_silhouette: Desenvolvedora 
[Virgínia Letícia Afonso](https://github.com/VLAfonso)

## :scroll: Licença
Este projeto está licenciado sob a MIT License.



