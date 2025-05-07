# Azure Language Studio

## 📅 Minha Jornada Inicial

**Primeiro dia:** 03/05/2025  
- Criei minha conta gratuita no Azure
- Ativei o serviço Language Studio na região Brazil South
- Gerei minhas primeiras chaves de API

**Dificuldade inicial:**  
"Demorei 20 minutos para encontrar onde criar o recurso no portal Azure!"

## 🛠️ Configuração Básica

### Passos que segui:
1. Acessei [portal.azure.com](https://portal.azure.com)
2. Busquei por "Language Service"
3. Selecionei o tipo F0 (gratuito)
4. Configurei na região `Brazil South`

## 🔍 Testes Realizados

### 1. Análise de Sentimentos
**Frase teste:**  
"Gosto do serviço, porém o preço poderia ser melhor"

**Resultado obtido:**
```json
{
  "sentiment": "mixed",
  "confidenceScores": {
    "positive": 0.6,
    "neutral": 0.1,
    "negative": 0.3
  }
}
```

### 2. Extração de Frases-Chave
**Texto analisado:**  
"O notebook tem boa bateria, mas o teclado não é confortável"

**Frases identificadas:**
1. "notebook tem boa bateria"
2. "teclado não é confortável"

## 💡 Lições Aprendidas

### O que funcionou bem:
- Reconhecimento preciso em português
- Rápido para textos curtos
- Integração fácil com Python

### Problemas encontrados:
1. **Limite de caracteres:**  
   Solução: Dividir textos longos em partes

2. **Erro 429 (Too Many Requests):**  
   Solução: Adicionei pausas entre requisições


## 📊 Meu Progresso

| Data       | Conquista | Dificuldade |
|------------|-----------|-------------|
| 03/05/2025 | Primeira análise | Configuração inicial |
| 04/05/2025 | Processei 100 textos | Limite de requisições |
| 04/05/2025 | Criei um arquivo de legendas .srt | Sincronizar a legenda com a fala do video |

## 🚀 Próximos Passos

- [ ] Testar reconhecimento de entidades
- [ ] Experimentar com arquivos PDF
- [ ] Criar um dashboard simples

> **Dica:** Comece com poucos textos para entender como funciona antes de escalar!


# Conhecendo Azure Speech Studio

## 🎙️ Primeiras Impressões

## 🔧 Configuração Inicial

### Passo a Passo que Segui:
1. Criei um recurso no Azure Portal:
   - Tipo: `Speech Service`
   - Camada: `Free F0` (até 5h/mês gratuitas)
   - Região: `Brazil South`

2. Acessei o [Speech Studio](https://speech.microsoft.com/)


## 🗣️ Funcionalidades Testadas

### 1. Texto para Voz (TTS)
**Teste realizado:**  
Converti o texto "Olá mundo, esta é minha primeira síntese de voz" usando:
- Voz masculina: `pt-BR-AntonioNeural`
- Voz feminina: `pt-BR-FranciscaNeural`

**Descoberta:**  
Adicionando SSML consegui controlar a entonação:
```xml
<speak version="1.0" xmlns="http://www.w3.org/2001/10/synthesis" xml:lang="pt-BR">
  <voice name="pt-BR-AntonioNeural">
    Olá <break time="300ms"/>, como vai você?
  </voice>
</speak>
```

### 2. Fala para Texto (STT)
**Experiência interessante:**  
Gravei um áudio dizendo "Hi, Azure Speech Studio" e o serviço transcreveu perfeitamente, incluindo a pontuação quando disse "ponto final".

## 💡 Insights Valiosos

### O que Aprendi:
1. **Qualidade de Áudio:**  
   - Usando um microfone externo melhorou muito precisão
   - Formato ideal: WAV mono 16kHz

2. **Limitações:**
   - Free tier permite apenas 5h de áudio/mês
   - Máximo de 10 requisições simultâneas

3. **Dica de Performance:**  
   Reutilizar objetos de configuração ao invés de criar novos para cada requisição.

## 📊 Meu Progresso

| Data       | Marco Alcançado | Desafio Superado |
|------------|-----------------|------------------|
| 06/05 | Primeira síntese de voz | Configurar ambiente |
| 06/05 | Transcrevi 10 áudios | Qualidade do microfone |


## 🐞 Problemas e Soluções

**Problema 1:** Áudio não sendo reconhecido  
**Solução:** Adicionei este tratamento de erro que encontrei pela internet:

```python
if result.reason == speechsdk.ResultReason.NoMatch:
    print("Não entendi. Tente novamente com um microfone melhor.")
```

**Problema 2:** Voz robótica  
**Solução:** Ajustei a prosódia via SSML:
```xml
<prosody rate="15%" pitch="10%">Texto mais natural</prosody>
```

## 🚀 Próximos Passos

- [ ] Experimentar tradução em tempo real
- [ ] Integrar com um bot no Teams
- [ ] Testar com arquivos de áudio longos

> **Dica de Iniciante:** Comece testando direto no portal antes de codificar - a ferramenta de demonstração é excelente para entender as capacidades!

📅 **Última Atualização:** 06/05/2025
Esta é meu primeiro dia utilizando o Azure Speech Studio, ainda tenho muito que aprender 
