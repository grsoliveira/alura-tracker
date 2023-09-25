# alura-tracker

Projeto em VUE.JS versão 3, realizado como exercício do curso de VUE.JS da Alura

## Criação e primeira execução do projeto
```
vue create alura-tracker

cd alura-tracker

npm run serve
```

## Instalação e Configuração do Bulma e FontAwsome

Para o uso do Bulma

Visitando https://bulma.io/documentation/overview/start/

Copiando ![img.png](img.png) para o head do index.html


Para o uso do FontAwnsome

executar o comando 
```
npm i --save-dev @fortawesome/fontawesome-free
```

import no arquivo main.ts
```
import '@fortawesome/fontawesome-free/css/all.css'
```


## Primeiro componente

Estado do componente é definido pela função interna data()

Valores calculados devem ser definidos dentro do atributo computed()

Todos os métodos do componente devem ser definidos dentro do atributo methods


## Passando informação entre componentes

A passagem de parametros entre componentes é realizada através do : (dois pontos)

```
<Cronometro :tempoEmSegundos="tempoEmSegundos"/>
```

## Linkando propriedades com o estado do componente

O link entre propriedades do html e elementos do estado da aplicação pode ser feito utilizando : (dois pontos)

```
<button class="button" @click="finalizar" :disabled="!cronometroRodando">
```
No angular, utilizamos o [(ngModel)] para realizar este mesmo binding.

Uma outra forma de realizarmos binding de elementos (inputs) do HTML com o estado do componente é utilizando v-model

```
<input type="text" class="input" placeholder="Qual tarefa você deseja iniciar?" v-model="descricao">
...
data() {
    return {
      descricao: ''
    }
}
```


## Emitindo eventos com o componente

A emissão de eventos do componente dá-se por meio do atributo emits.

Por fim, para emitir o evento, é necessário invocar a função $emit passando o nome do evento e o payload (dados) a serem compartilhados. 

```
emits: ['aoTemporizadorFinalizado'],
...

this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos);
```

Para tratar (capturar) o evento disparado, realizarmos a mesma operação que fazemos quando vamos escutar um @click

```
<Temporizador @aoTemporizadorFinalizado="finalizarTarefa" />

...

methods: {
    finalizarTarefa(tempoDecorrido: number): void {
      //corpo
    }
}
```

## Criando uma lista de elementos

Utilizamos a diretiva v-for para iterar sobre uma lista

```
<TarefaComp v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
```
