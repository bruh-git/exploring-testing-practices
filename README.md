# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar um repositório

Escolha um repositório real que possua testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar o repositório selecionado

Busque o repositório escolhido no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar uma prática de teste

Escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

Repositório: https://github.com/psf/requests

URL TestMiner: https://andrehora.github.io/testminer/#psf/requests

Explicação: No arquivo [`tests/conftest.py`](https://github.com/psf/requests/blob/main/tests/conftest.py), o projeto utiliza a fixture `clean_proxy_environ` com `autouse=True` para remover automaticamente variáveis de ambiente de proxy, como `HTTP_PROXY` e `HTTPS_PROXY`, antes de cada teste. Isso evita que a configuração de rede da máquina do desenvolvedor ou do ambiente de integração contínua altere inesperadamente os resultados, tornando os testes mais isolados e reproduzíveis. O mesmo arquivo centraliza fixtures reutilizáveis para URLs de teste e um servidor HTTPS local, reduzindo a repetição de configuração. O uso de `monkeypatch` também permite que as alterações no ambiente sejam revertidas ao fim do teste.

**Evidência no TestMiner:** a visão geral classifica 10 arquivos como testes, 12 como auxiliares de teste e 1 como teste de integração contínua. A seção *Test History* sugere que a quantidade de arquivos classificados como testes aumentou nas versões exibidas, chegando a 10 na versão mais recente mostrada. Em *Test Dependencies*, aparecem bibliotecas usadas no contexto de testes, como `pytest`, `pytest-cov` e `pytest-httpbin`. Isso ajuda a observar a organização e a evolução dos testes, embora a classificação do TestMiner, por si só, não prove que todos os testes passam ou que a cobertura é suficiente.

Visão do Requests no TestMiner: Overview, Test Location, Test History e Test Dependencies <img width="771" height="899" alt="image" src="https://github.com/user-attachments/assets/9280fc4f-188a-4db1-81ec-a84a86833399" />

[Consultar a análise interativa do Requests no TestMiner](https://andrehora.github.io/testminer/#psf/requests)
