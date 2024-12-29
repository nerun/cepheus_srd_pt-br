# Manifesto apologético do formato universal

## Um formato que perdura no tempo

O padrão [Unicode](https://en.wikipedia.org/wiki/Unicode) foi uma revolução ao transcender as limitações das codificações de caracteres tradicionais, como ASCII, porque o Unicode suporta outros caracteres além dos 128 disponíveis no idioma inglês, o que o torna universal. E o formato [UTF-8](https://en.wikipedia.org/wiki/UTF-8) foi mestre na implementação do padrão Unicode ao incorporar ASCII. Na verdade, ASCII é agora um subconjunto do UTF-8.

Esta informação é relevante porque o formato ASCII sobreviveu ao tempo e é considerado um dos melhores formatos para armazenar textos eletrônicos (e-textos) que perduram no tempo. A maioria dos romances, livros, contos e histórias de domínio público disponíveis no [Projeto Gutenberg](https://www.gutenberg.org) estão no formato UTF-8.

Nas palavras do Projeto Gutenberg:[^1]

> _O ponto principal de tudo isso é que daqui a alguns anos os textos eletrônicos do Projeto Gutenberg ainda serão viáveis, mas programa após programa, e sistema operacional após sistema operacional terão o mesmo destino dos dinossauros, assim como todas aqueles componentes de hardware usados para executá-los. Claro, isso é válido para todos os textos eletrônicos escritos no Padrão ASCII Puro... E não apenas aqueles que você obteve do Projeto Gutenberg. A questão é que daqui a uma década provavelmente não teremos os mesmos sistemas operacionais, ou os mesmos programas e, portanto, todos os vários tipos de textos eletrônicos que não são Padrão ASCII Puro estarão obsoletos. Precisamos ter textos eletrônicos em arquivos com os quais um programa de leitura de texto simples possa lidar; isso não quer dizer que nunca deva haver qualquer marcação... Apenas que essas formas de marcação devem ser facilmente conversíveis em arquivos Padrão ASCII Puro convencionais, para que sua utilidade não expire quando os programas para usá-los não estiverem mais entre nós. Você se lembra de todos os problemas com programas de conversão para converter arquivos de processadores de texto antigos para o Padrão ASCII Puro?_

## Markdown

Claro, o Projeto Gutenberg só aceita [texto puro](https://pt.wikipedia.org/wiki/Texto_simples) (arquivos .txt em UTF-8), mas [markdown](https://en.wikipedia.org/wiki/Markdown) é uma linguagem de marcação que é _essencialmente_ texto puro, ou seja, tem a mesma legibilidade quando lido em um editor de texto simples.

Markdown é uma linguagem de marcação leve (ou humana) com sintaxe simples e discreta. Ele foi projetado para ser fácil de escrever usando qualquer editor de texto genérico e fácil de ler em sua forma bruta. Markdown é uma linguagem de marcação destinada à criação de texto formatado usando qualquer editor de texto simples. Na verdade, é tão simples e discreto que uma pessoa pode abrir um arquivo markdown (extensão ".md") e lê-lo como se fosse um arquivo de texto puro. Você pode renomear sua extensão para ".txt" se preferir. No Windows, basta usar o bloco de notas, e no Linux abundam os editores de texto simples: gedit (e suas variantes), kate, emacs, vim, nano etc.

## Uma linguagem intercambiável

Arquivos escritos no formato UTF-8 usando linguagem markdown não são apenas fáceis de ler e abrir em qualquer sistema operacional e software editor de texto simples, mas também são fáceis de converter para qualquer formato profissional ou mais complexo.

A maneira mais fácil de fazer isso é importar seu conteúdo diretamente para um editor de texto do **LibreOffice** ou do **Microsoft Office**, ou para editores de publicações profissionais como **Scribus** ou **Adobe InDesign**.

No entanto, o programa [pandoc](https://pandoc.org) está disponível para vários sistemas operacionais: Windows, Linux, BSD, macOS etc. E é gratuito e de código aberto.

Claro, pandoc é uma ferramenta de linha de comando, projetada para ser usada em prompt de comando, powershell, terminal Linux etc., mas é tão fácil quanto escrever isto:

```shell
$ pandoc arquivo.md -f markdown -t docx -s -o arquivo.docx
```

O `arquivo.md` informa ao pandoc qual arquivo converter. A opção `-s` diz para criar um arquivo "autônomo", com cabeçalho e rodapé, não apenas um fragmento. E `-o arquivo.docx` diz para colocar o resultado da conversão no arquivo `arquivo.docx`. Observe que poderíamos ter omitido `-f markdown -t docx`, já que o pandoc é inteligente o suficiente para entender a natureza do arquivo de entrada e de saída, mas não custa nada incluí-los.[^2]

A aparência geral do arquivo convertido é muito boa e não há do que reclamar.

27 de Julho de 2023 (_revisado em 19 de Maio de 2024_)

**Daniel Dias Rodrigues**


[^1]: Hart, Michael (1992, August). _The History and Philosophy of Project Gutenberg_. Project Gutenberg. https://www.gutenberg.org/about/background/history_and_philosophy.html

[^2]: _Getting started with pandoc: Step 6 - Converting a file_. Pandoc: a universal document converter. https://pandoc.org/getting-started.html#step-6-converting-a-file