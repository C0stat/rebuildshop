# Integração proposta com a SP-API

## Finalidade e tipo de aplicação

Aplicação privada para apoiar decisões de abastecimento e precificação da RebuildShop em sua própria operação de vendas na Amazon. O acesso pretendido é o de desenvolvedor privado, para integrar a própria empresa.

A integração ainda está em planejamento. As capacidades abaixo dependem da aprovação da Amazon, dos papéis concedidos, da disponibilidade das operações no marketplace e da implementação posterior.

## APIs previstas

| API | Uso proposto | Referência oficial |
| --- | --- | --- |
| Catalog Items | Identificar e consultar itens do catálogo que a RebuildShop pretende avaliar para revenda. | [Catalog Items API](https://developer-docs.amazon.com/sp-api/docs/catalog-items-api) |
| Listings Restrictions | Consultar restrições de listagem por ASIN para a conta da RebuildShop, o marketplace e a condição pretendida. | [Listings Restrictions API](https://developer-docs.amazon.com/sp-api/docs/listings-restrictions-api) |
| Product Pricing | Consultar informações de preços e ofertas para subsidiar a precificação da própria operação. | [Product Pricing API](https://developer-docs.amazon.com/sp-api/docs/product-pricing-api) |
| Product Fees | Obter estimativas de tarifas para os produtos e preços avaliados. | [Product Fees API](https://developer-docs.amazon.com/sp-api/docs/product-fees-api) |

O escopo inicial poderá ser atendido pelos papéis **Product Listing** e **Pricing**, conforme as operações escolhidas e a avaliação da Amazon. A solicitação deverá limitar-se aos papéis necessários ao uso descrito.

## Interpretação de “ASIN aberto”

No projeto, essa expressão significa a triagem de itens para os quais a consulta não retorna restrições de listagem para a conta da RebuildShop, no marketplace e na condição consultados, naquele momento.

O resultado não substitui requisitos de autenticidade, procedência, documentação, direitos de marca ou políticas de venda. Quando houver necessidade de aprovação, o item deverá seguir o processo indicado pela Amazon. Falhas de consulta ou respostas inconclusivas não deverão ser classificadas como liberação para venda.

## Margem estimada

A análise combinará o preço de venda avaliado com as estimativas de tarifas da Amazon e os custos próprios disponíveis: aquisição, fretes, embalagem, tributos e demais despesas aplicáveis. Custos já incluídos nas tarifas deverão ser identificados para evitar dupla contagem.

```text
Resultado unitário estimado = receita de venda considerada
                           - tarifas estimadas da Amazon
                           - custo de aquisição
                           - logística e embalagem não incluídas nas tarifas
                           - tributos e demais despesas alocadas

Margem estimada (%) = resultado unitário estimado / receita de venda considerada × 100
```

O cálculo pressupõe receita positiva e custos completos. Informações ausentes deverão ser sinalizadas, sem aprovação automática do item. O limite mínimo de margem será definido pela RebuildShop durante a implementação; não há percentual estabelecido nesta documentação.

O resultado será uma estimativa para apoio à decisão, sem garantia de rentabilidade ou de volume de vendas. A própria Amazon informa que as tarifas efetivas podem divergir das estimativas da Product Fees API.

## Tratamento previsto dos dados

- Usar os dados somente para a operação interna autorizada da RebuildShop, conforme as políticas da Amazon.
- Limitar as consultas às informações necessárias para avaliar itens que a empresa pretende listar.
- Não incluir dados pessoais de compradores no escopo inicial, nem vender ou redistribuir dados obtidos das APIs.
- Manter credenciais, tokens, identificadores de conta e dados comerciais fora do repositório público.
- Definir e validar os controles de acesso, proteção de credenciais, retenção e exclusão antes da entrada em produção.
- Respeitar os limites de requisição e tratar erros sem presumir elegibilidade ou margem favorável.

Esses itens descrevem requisitos para a futura implementação. Este repositório documental não atesta controles implantados nem certificação de conformidade.

## Documentação de referência

- [Cadastro como desenvolvedor privado](https://developer-docs.amazon.com/sp-api/docs/register-as-a-private-developer)
- [Guia de gerenciamento de listagens e pesquisa de catálogo](https://developer-docs.amazon.com/sp-api/docs/manage-product-listings-guide)
- [Papéis da Selling Partner API](https://developer-docs.amazon.com/sp-api/docs/roles-in-the-selling-partner-api)
- [Políticas e acordos da Amazon](https://developer-docs.amazon.com/sp-api/docs/policies-and-agreements)
