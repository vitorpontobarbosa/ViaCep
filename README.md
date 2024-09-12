# ViaCEP Collection

Esta Collection abrange as chamadas dos serviços de **Validação de CEP** e **Pesquisa de CEP**.

## Casos de Teste

### Serviço de Validação de CEP:
Foram criados três casos de teste para validar diferentes cenários:
- **ValidaCepError**: Envia um CEP válido, mas inexistente. O serviço deve retornar um status code **200** com `"erro": true` no corpo da resposta.
- **ValidaCepBadRequest**: Envia um valor inválido (alfanumérico). O serviço deve retornar um status code **400**.
- **ValidaCepSuccess**: Envia um CEP válido e existente. O serviço deve retornar os dados correspondentes a esse CEP.

### Serviço de Pesquisa de CEP:
Cinco casos de teste foram definidos para este serviço:
- **PesquisaCepSuccess**: Envia dados válidos e o serviço retorna um status **200** com o endereço e o CEP no corpo da resposta.
- **PesquisaCepNotFound**: Envia valores válidos, mas sem resultados. O serviço retorna um status **200** com um array vazio.
- **PesquisaCepRuaBadRequest**: Envia um valor inválido para o campo "Rua". O serviço deve retornar um status code **400**.
- **PesquisaCepCidadeBadRequest**: Envia um valor inválido para o campo "Cidade". O serviço deve retornar um status code **400**.
- **PesquisaCepEstadoBadRequest**: Envia um valor inválido para o campo "Estado". O serviço deve retornar um status code **400**.

## Testes de Performance

Realizei testes de performance com **ramp-up** para avaliar se o tempo de resposta aumentaria ao longo do tempo. No entanto, após a primeira execução (que ainda precisava de ajustes), a API bloqueou meu acesso, possivelmente por questões de segurança, e não consegui repetir os testes. Nas tentativas seguintes, não obtivemos resposta do servidor.
