# whats-sleepSort

![Sleep sort](https://github.com/JonanthaW/whats-sleepSort/blob/main/sleepSort.png "Sleep sort header")

[![Profile Linkedin](https://img.shields.io/badge/Profile-Linkedin-blue)](https://pt.linkedin.com/pulse/voc%C3%AA-j%C3%A1-ouviu-falar-em-sleep-sort-jonantha-willian) ![Github](https://img.shields.io/badge/Status-Complete-green)

O **Sleep sort** é um algoritmo time-based de **ordenação** (posiciona os elementos de uma sequência/lista em uma certa ordem utilizando tempo como parâmetro) de **autoria desconhecida** apresentado pela primeira vez num relato de entrevista de emprego na [**Google**](gafter.blogspot.com/2006/11/linear-time-sort-puzzler.html?m=1) e difundido anonimamente no [**4chan**](https://web.archive.org/web/20151231221001/http://bl0ckeduser.github.io/sleepsort/sleep_sort_trimmed.html).

Neste algoritmo nós criamos diferentes threads para **cada um dos elementos na sequência/lista** e colocamos cada um deles para "dormir" pela quantia de tempo proporcional ao seu valor correspondente.

* Se o elemento for o número 5, ele vai dormir por 5 segundos;
* Se for o número 40, vai dormir por 40 segundos;

A thread que "dorme" menos, por lógica, acorda primeiro sendo jogada ordenada em uma nova array, seguida sucessivamente pelas próximas.

``` Pseudocódigo:
`
   para n em array:
       criar nova thread e fazer ela esperar por array[n] milissegundos
       escrever array[n]
   finalizar  
   esperar todos processos finalizarem
```

Utilizamos a função *"sleep"* para adormecer uma thread até certa condição ser atingida (geralmente uma quantia de segundos determinada). Com a grande variedade de linguagens essa função pode receber outros nomes, como no JavaScript que se chama *"setTimeout"*, ou em Haskell que é chamada de *"ThreadDelay"*.

A complexidade do Sleep Sort é bem contraditória. Alguns dizem ser  *"O(n * log(n))"*, outros dizem ser *"O(max(input)+n)"*, e tem quem diga ser *"O(NlogN + max(input))"*.

<div align="center">
   <img src="https://github.com/JonanthaW/whats-sleepSort/blob/main/example.gif"/>
</div>

**Mas nem tudo é sombra e água fresca.** O tanto de problemas que tem nesse treco não dá pra contar nos dedos.

* Vamos falar logo dos mais propícios a acontecer:
* Se os valores estiverem muito próximos, o algoritmo não consegue ordenar satisfatóriamente. Como exemplo podemos citar os números "0" e "1" que têm a mesma duração para o sistema (1 segundo);
* TODOS dados devem ser obrigatoriamente positivos (Não é possível "dormir" uma quantia negativa de tempo (ou será que é?));
* Dados/entradas grandes diminuem drasticamente a velocidade da ordenação (já que o subprocesso vai "dormir" sua quantia em tempo real). Um número como "1.000.000" demoraria mais de 16 minutos para ser ordenado;
* O sistema em que o algoritmo está sendo executado pode gerar uma saída errada já que podem ocorrer variações vindas de outras operações, como mudanças de prioridade agendadas, lentidões em sistemas mais antigos, interferências de outros processos, falta de threads disponíveis, etc.

**Nem preciso te dizer que ela não tem aplicação efetiva no mundo real, não é?** No máximo você vai utilizar ela pra estudar multithread ou pra matar a curiosidade em alguma situação MUITO específica.

Existem muitas maneiras de escrever um Sleep Sort.

Em JavaScript podemos citar:

Para escrevermos cada um dos elementos em ordem:
``` 
let sleepSort = () => {
   const Array_Inicial = [9, 16, 5, 71, 33];   
   Array_Inicial.forEach(n => {
      setTimeout(function() {
         console.log(n)
      }, n);
   });
}

sleepSort();
```

Para criarmos uma nova array de elementos em sequência:

``` 
let sleepSort = (...args) => {
   let Array_Sort = [];
   args.forEach(n => {
      setTimeout(function() {
         Array_Sort.push(n)
      }, n);
   })
}

sleepSort(9, 16, 5, 71, 33);
```
(Se você quiser ver como ficaria na sua linguagem de programação favorita, é so acessar este site aqui: [Sleep Sort em outras linguagens](https://rosettacode.org/wiki/Sorting_algorithms/Sleep_sort)).

<div align="center">
   <img src="https://github.com/JonanthaW/whats-sleepSort/blob/main/cont.jpeg"/ width="600px">
</div>
*E isso tudinho acontecendo láaaa no background do sistema. Tudinho feito pelo OS em suas entranhas eletrônicas.*

***Interessado neste assunto?** recomendo a você alguns vídeos e materias para se aprofundar:*
* [Sleep Sort ( Craziest Sorting Algorithm ) in 1 Minute with Visualisation & Code](https://www.youtube.com/watch?v=Cp9mdJmVtvo)
* [Sort Sleep 4](https://www.youtube.com/watch?v=pWlc6COonc8)
* [Sleep Sort – The King of Laziness / Sorting while Sleeping](https://www.geeksforgeeks.org/sleep-sort-king-laziness-sorting-sleeping/)
* [Sleep Sort: Where Theory meets Sobering Reality ](https://dev.to/sishaarrao/sleep-sort-where-theory-meets-sobering-reality-b3m)





~*SLEEP SORT*

~*If it works then it is not lazy.*


### :computer: Baixando o conteúdo:

```bash
$ git clone https://github.com/JonanthaW/Arduino-Projects.git
```
