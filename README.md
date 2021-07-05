<h1>A COVID-19 no município de Botucatu/SP e os primeiros efeitos da vacinação na progressão da pandemia </h1>

 
<img src="https://github.com/camilasp/Previsao_COVID-19/blob/master/images/pexels-markus-spiske-3970332.jpg" width="1000" height="500">

<h2>Objetivos do projeto:</h2>

*  analisar o número de casos e óbitos por Covid-19 no Estado de São Paulo e na cidade de Botucatu,  utilizando séries temporais referentes aos dados da epidemia no Estado;
* verificar se há indícios de mudança na progressão da pandemia, tanto do número de casos como do número de óbitos, após o recebimento da primeira dose pela população da cidade de Botucatu;
* elaborar previsões com relação à progressão da pandemia utilizando a ferramenta Facebook Prophet.

<h3> Hipótese: </h3>
<li> Já será possível perceber uma tendência de mudança nos números da pandemia na cidade de Botucatu (queda do número de casos, óbitos ou ambos) a partir do final de     junho/2021.</li>
<br>

 <h2> Sobre os dados </h2>
 
 <p>Os dados utilizados foram extraídos de três bases de dados diferentes:</p>

Do [site](https://brasil.io/dataset/covid19/caso_full/) Brasil IO, uma base de dados que contém os dados referentes aos casos confirmados e óbitos obtidos dos boletins das Secretarias Estaduais de Saúde (SES). Os dados foram enriquecidos, de forma que a partir do momento em que um município confirma um caso, ele sempre aparecerá nessa tabela (mesmo que para uma determinada data a SES não tenha liberado o boletim - nesse caso é repetido o dado do dia anterior).

Também foram utilizados dados da pandemia no Estado de São Paulo, obtidos da base de dados contida no [repositório](https://github.com/seade-R/dados-covid-sp) do SEADE e os dados sobre vacinação no Estado de São Paulo, extraídos do [site](https://www.saopaulo.sp.gov.br/planosp/simi/dados-abertos/) do estado de São Paulo.
<br>

<h2> Uma breve introdução ao tema</h2>

<h3> O que é a COVID-19?</h3>

<img src="https://github.com/camilasp/Previsao_COVID-19/blob/master/images/pexels-cdc-3993212.jpg" align="right" width ="500" height="300">

<p> A COVID-19 é uma doença infecciosa causada pelo coronavírus da síndrome respiratória aguda grave 2(-SARS-CoV-2), 
cujo primeiro caso foi identificado na cidade de Wuhan na China em dezembro de 2019 e desde então se espalhou pelo mundo todo, ocasionando uma pandemia que ainda está em curso. 
No final de junho/2021, já haviam sido registrados 182 milhões de casos no mundo e 3.95 milhóes de mortes pela doença. No Brasil eram 18.6 milhões de casos e 512 mil óbitos. </p>
 
<p>A COVID-19 é transmida através de gotículas produzidas nas vias respiratórias das pessoas infetadas. Ao espirrar ou tossir, 
estas gotículas podem ser inaladas ou atingir diretamente a boca, nariz ou olhos de pessoas em contato próximo.Também podem depositar-se em objetos e 
superfícies próximos que podem infetar quem nelas toque e leve a mão aos olhos, nariz ou boca. O intervalo de tempo entre a exposição ao vírus e
o início dos sintomas é de 2 a 14 dias, sendo em média 5 dias.</p>
<br>


<h3> Como podemos parar a COVID-19?</h3>

<img src="https://github.com/camilasp/Previsao_COVID-19/blob/master/images/pexels-cottonbro-3952238%20(1).jpg" align="left" width ="400" height="300">

<p>Como ocorre na maioria das doenças virais, não há medicamentos que previnam nem tratamento específico cuja eficácia tenha sido
comprovada para a COVID-19. O manejo da doença é feito com base no alívio dos sintomas e de medidas mais intervencionionistas nos casos de doença grave,
onde costuma ser feita a intubação do paciente para que evitar os danos relacionados à baixa oxigênação ocasionada pela doença nesses casos.</p>

<p>A prevenção é baseada em bons hábitos de higiene, uso de mascaras que protejam da exposição às gotículas de saliva, no distanciamento social  e 
na vacinação da população.</p>
 

<p>Desde 2020, várias vacinas foram desenvolvidas e testadas e há uma variedade de vacinas disponíveis atualmente e a imunização da população já se iniciou 
em grande parte dos países. O Brasil, infelizmente, ainda não conseguiu vacinar uma parcela significativa da população. Até o dia 27 de junho de 2021, 70 325 677 pessoas, 
quivalente a 33,21% da população brasileira, foram vacinadas com a 1.ª dose de uma das vacinas; a 2.ª dose foi aplicada em 25 243 190 pessoas, 
equivalente a 11,92% da população. </p>
<br>


<a>
<img src="https://github.com/camilasp/Previsao_COVID-19/blob/master/images/pexels-nataliya-vaitkevich-5863389.jpg" width ="400" height="300" align= "right">
 </a>
 <h3> As vacinas contra a COVID-19 são eficazes?</h3>

<p> As diversas vacinas disponíveis contra COVID-19 estão sendo amplamente estudadas no mundo todo, buscando entender sua efetividade e seus efeitos na contenção da pandemia.</p>

<p>Nenhuma das vacinas disponíveis no mundo atualmente tem eficácia de 100% contra o vírus Sars-CoV-2, ou seja, elas não impedem que o indivíduo seja infectado e passe a doença para outras pessoas. Mas elas são eficazes de evitar os casos graves da doença, que levam à intubação e à morte.</p>
<br>

<h3> Quanto tempo demora para fazerem efeito?</h3>

<p>As vacinas se mostraram eficientes em evitar que a doença seja contraída e transmitida, mas além disso mostraram alta eficácia na diminuição da gravidade da doença, quando contraída. A vacina Oxford/AstraZeneca, por exemplo, conferiu eficácia de mais de 70% na primeira dose, 22 dias após a aplicação. Após a segunda dose, a eficácia chega a quase 100% para casos graves e morte, desde que se tome as duas no período recomendado – 12 semanas. </p>

<p>No Brasil, há cidades que estão participando em estudos da efetividade da vacinação contra a COVID-19. Este é o caso da cidade estudada neste projeto, a cidade de Botucatu localizada no estado de São Paulo. Em 27 de abril de 2021, Botucatu foi escolhida pelo Ministério da Saúde para iniciar a vacinação em massa na população acima de 18 anos. A vacina utilizada é a vacina produzida pela AstraZeneca em parceria com a Fiocruz. A campanha foi iniciada em 16/maio/2021, quando 65 000 dos cerca de 147 000 habitantes da cidade receberam a primeira dose da vacina. No final de junho mais de 81% da população da cidade já havia recebido a primeira dose.</p>
<br>


Acesse o [notebook](https://github.com/camilasp/Previsao_COVID-19/blob/master/notebooks/Projeto_3.ipynb) para ver o projeto todo, incluindo análise dos dados, desenvolvimento de previsões usando o Prophet e conclusões.
<br>
<br>

<h3> Referências<h3>
<li> https://brasil.io/dataset/covid19/caso_full/
<li> https://github.com/seade-R/dados-covid-sp
<li> https://www.saopaulo.sp.gov.br/planosp/simi/dados-abertos/
<li> https://covid.saude.gov.br/
<li> https://en.wikipedia.org/wiki/COVID-19
<li> https://blog.brasil.io/2020/03/23/dados-coronavirus-por-municipio-mais-atualizados/
<li> https://brasil.io/dataset/covid19/caso_full/
<li> https://g1.globo.com/sp/bauru-marilia/noticia/2021/05/16/vacinacao-em-massa-termina-com-mais-de-65-mil-doses-da-astrazeneca-aplicadas-em-botucatu.ghtml
<li> https://exame.com/brasil/botucatu-tem-queda-de-48-em-casos-de-covid-5-semanas-apos-vacinacao/
<li> https://www.cnnbrasil.com.br/saude/2021/06/28/covid-19-vacinacao-em-massa-em-botucatu-sp-reduz-casos-em-71
<li> https://www.bbc.com/portuguese/geral-56916558
<li> https://www.cnnbrasil.com.br/saude/2021/05/19/vacina-nao-impede-de-contrair-covid-19-mas-evita-gravidade-e-morte-entenda
<li> https://g1.globo.com/bemestar/vacina/noticia/2021/05/01/vacina-astrazeneca-entenda-qual-a-protecao-da-1a-dose-e-qual-o-motivo-do-intervalo-de-tres-meses-para-a-2a.ghtml
<li> Foto de cottonbro no Pexels
<li> Foto de CDC no Pexels
<li> Foto de Markus Spiske no Pexels

