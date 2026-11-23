# RebuildShop

**Comércio eletrônico e pesquisa de produtos para a própria operação de vendas.**

A RebuildShop comercializa produtos na Amazon e está planejando uma ferramenta interna para apoiar a seleção de itens para revenda, a verificação de restrições de listagem e a análise de margem estimada.

Este é o repositório público de apresentação da organização e da integração proposta com a Amazon Selling Partner API (SP-API).

## Projeto: RebuildShop — análise de catálogo

A ferramenta proposta será de uso exclusivo da RebuildShop, vinculada à sua própria conta de vendedor. O objetivo é apoiar decisões de abastecimento e precificação de produtos que a empresa pretende comercializar na Amazon.

O fluxo planejado compreende:

1. Pesquisar e identificar itens do catálogo relevantes para a operação.
2. Consultar restrições de listagem de cada ASIN para a conta da RebuildShop, o marketplace e a condição do produto.
3. Consultar informações de preços e estimativas de tarifas disponíveis nas APIs autorizadas.
4. Combinar essas informações com custos próprios de aquisição, logística e demais despesas aplicáveis.
5. Selecionar itens que atendam aos critérios internos de margem para revisão antes da compra e da criação de ofertas.

A ausência de restrições retornadas em uma consulta não representa autorização permanente para vender um produto. Preços, tarifas e margem são estimativas sujeitas a variação.

## Status

**Planejamento da integração e solicitação de acesso à SP-API.** Este repositório contém documentação; não contém uma automação operacional nem comprova aprovação de acesso pela Amazon.

O projeto é uma ferramenta interna. Não há oferta de software a terceiros ou planos comerciais de assinatura.

## Dados e acesso previstos

O escopo proposto inclui informações de catálogo, restrições de listagem, preços, estimativas de tarifas e custos da própria operação. Não inclui dados pessoais de compradores nem acesso a contas de outros vendedores.

As consultas dependerão das permissões concedidas pela Amazon e deverão observar suas políticas e limites de uso. Este repositório público destina-se somente à documentação, sem credenciais ou dados operacionais da empresa.

Veja o [escopo da integração proposta](docs/sp-api.md), com as APIs previstas e seus limites.

## Identificação e contato cadastral

**Organização:** RebuildShop.

Os dados de contato da organização são fornecidos diretamente à Amazon no cadastro de desenvolvedor. Este repositório não publica e-mail ou outros dados pessoais de contato.

## English overview

RebuildShop sells products on Amazon and is planning a private, internal application for its own seller account. The proposed application will support catalog research for sourcing decisions, seller-specific listing restriction checks, pricing and fee estimates, and estimated margin analysis using the company's own costs.

SP-API access is being requested. This repository provides organization and project documentation; it does not contain a working integration or represent Amazon approval. The intended scope excludes buyer personal information, third-party seller accounts, and the sale or redistribution of Amazon API data. Organization contact details are provided directly to Amazon through the developer registration process.

---

Amazon e SP-API são referências aos serviços utilizados na integração proposta. A RebuildShop não declara parceria, certificação ou endosso da Amazon.
