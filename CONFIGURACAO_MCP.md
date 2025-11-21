# 📋 Guia de Configuração do MCP Server de PDF

## ✅ O que já foi feito:

1. ✅ Python 3.13.7 instalado e funcionando
2. ✅ Servidor MCP de PDF instalado com sucesso
3. ✅ Todas as dependências instaladas (mcp, pypdf2, pytesseract, pymupdf, etc.)

## 🔧 Como Configurar no Cursor:

### Opção 1: Configuração via Interface do Cursor (Recomendado)

1. Abra o Cursor
2. Pressione `Ctrl + Shift + P` (ou `Cmd + Shift + P` no Mac)
3. Digite: "Preferences: Open User Settings (JSON)"
4. Adicione esta configuração:

```json
{
  "mcpServers": {
    "pdf-extraction": {
      "command": "python",
      "args": [
        "-m",
        "pdf_extraction"
      ],
      "cwd": "C:\\Users\\victo\\OneDrive\\Área de Trabalho\\IA - Escola de Produto\\mcp-pdf-extraction-server"
    }
  }
}
```

### Opção 2: Arquivo de Configuração Manual

O Cursor pode usar um arquivo de configuração específico. Crie um arquivo chamado `.cursor/mcp.json` na raiz do seu projeto com o conteúdo acima.

## 🚀 Como Usar:

Depois de configurado, você pode me pedir:

- **"Extraia o conteúdo do PDF X.pdf"**
- **"Leia as páginas 1, 3 e 5 do arquivo Y.pdf"**
- **"Extraia a última página do PDF Z.pdf"** (use "-1" para última página)
- **"Leia o PDF escaneado W.pdf"** (suporta OCR automático)

## 📝 Exemplos de Uso:

### Exemplo 1: Extrair todo o PDF
```
"Extraia todo o conteúdo do arquivo 2024-wttc-introduction-to-ai.pdf"
```

### Exemplo 2: Páginas específicas
```
"Extraia as páginas 1, 3, 5 e a última página do PDF Factorial One_Brand Book (1).pdf"
```

### Exemplo 3: PDF escaneado (com OCR)
```
"Leia o PDF escaneado X.pdf usando OCR"
```

## ⚠️ Notas Importantes:

1. **Caminhos no Windows**: Use barras duplas `\\` ou barras normais `/` nos caminhos
2. **Caminhos com espaços**: O caminho já está configurado corretamente
3. **Reiniciar o Cursor**: Após configurar, reinicie o Cursor para que as mudanças tenham efeito

## 🔍 Verificar se está funcionando:

Após configurar e reiniciar o Cursor, você pode me perguntar:
- "Liste os servidores MCP disponíveis"
- "Extraia uma página de teste de um PDF"

Se eu conseguir acessar o servidor, significa que está funcionando!

## 📚 Recursos do Servidor:

- ✅ Extração de texto de PDFs normais
- ✅ OCR para PDFs escaneados (suporta chinês e inglês)
- ✅ Extração de páginas específicas
- ✅ Suporte a índices negativos (-1 = última página)
- ✅ Múltiplas páginas separadas por vírgula (ex: "1,3,5,-1")

## 🆘 Troubleshooting:

### Se não funcionar:

1. Verifique se o Python está no PATH: `python --version`
2. Teste o módulo diretamente: `python -m pdf_extraction` (vai ficar esperando, isso é normal)
3. Verifique se o caminho no JSON está correto
4. Reinicie o Cursor completamente

### Para PDFs escaneados (OCR):

O servidor usa Tesseract OCR. Se precisar de OCR, você pode precisar instalar o Tesseract separadamente:
- Windows: https://github.com/UB-Mannheim/tesseract/wiki
- Mas geralmente funciona sem instalação adicional para PDFs normais

---

**Status da Instalação:** ✅ COMPLETA
**Próximo Passo:** Configure no Cursor usando uma das opções acima

