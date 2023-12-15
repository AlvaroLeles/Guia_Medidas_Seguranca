# Referencial

Para a produção deste guia, foram realizadas pesquisas no ambiente bibliográfico acerca de boas práticas para o desenvolvimento web focado em se precaver em relação à exposição de dados sensíveis. Esse guia se baseia na metodologia de desenvolvimento seguro da Microsoft, o SDL e nas práticas de desenvolvimento seguro recomendadas pela OWASP, com foco na prevenção da exposição de dados sensíveis.

Além da base bibliográfica, esse guia também se escora na pesquisa documental, em cima de análises de casos de exposição de dados sensíveis em empresas globais de grande porte. Os casos analisados para a construção desse guia pertencem às seguintes empresas:

- LinkedIn, plataforma profissional para networking e oportunidades de carreira, que passou por vazamentos de dados em 2021;
- Yahoo, portal de internet que oferece serviços variados comomecanismo de busca, e-mail, notícias e entretenimento, que passou porvazamentos nos anos de 2013 e 2016;
- eBay, plataforma de comércio eletrônico que facilita a compra evenda de produtos entre usuários, que sofreu um ataque em 2014;
- Equifax, empresa de serviços de informação de crédito que avalia efornece relatórios de crédito para indivíduos e empresas, auxiliando emdecisões de crédito e gestão de riscos financeiros, que teve dados vazadosem 2017;
- JPMorgan Chase, instituição financeira global, que oferece serviços bancários, financeiros e de gestão de ativos para clientes corporativos,institucionais e individuais, que teve dados expostos em 2014;
- Target, rede varejista americana, contando com lojas físicas eonline, que teve seus dados expostos em 2013.

As recomendações presentes a seguir foram inspiradas nesses casos, o que não significa que este documento seja um guia definitivo, mas sim que foi baseado em casos reais, buscando trazer práticas que podem prevenir algumas das várias situações reais de ataque em plataformas web.

A principal referência para a construção desse guia é o livro "Big Breaches - Cybersecurity Lessons for Everyone", onde mais de 9 mil vazamentos foram estudados, trazendo os mais relevantes para o livro e ao final sugerindo práticas de segurança para evitar as principais causas raiz encontradas em sua pesquisa.