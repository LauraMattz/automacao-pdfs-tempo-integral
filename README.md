# 📊 Scraper de Relatórios de Prefeitos - Programa Tempo Integral

Automação para download e extração de dados de 5.570 relatórios municipais em PDF do programa Tempo Integral do MEC.

## 🎯 O Problema

Precisava extrair informações específicas de **5.570 PDFs** (um para cada município brasileiro). Fazer isso manualmente levaria **232 horas** (~29 dias úteis de trabalho).

## ✨ A Solução

Script Python que automatiza todo o processo:
- ⬇️ Download automático dos 5.570 PDFs
- 📄 Extração de dados das páginas 5-10
- ⚡ Processamento paralelo para otimizar velocidade
- 💾 Salvamento incremental no Google Drive
- 📊 Exportação organizada em CSV

## 🚀 Resultados
- ⚡ **38,7 PDFs/minuto** processados
- 💰 **R$ 5,7 bilhões** em recursos mapeados
- ⏱️ **8h24min** total vs **232 horas** manual

## 📋 Pré-requisitos
```bash
pip install pandas requests tqdm pypdf2
```

Para usar no Google Colab (recomendado):
- Conta Google (para salvar no Drive)
- Espaço no Drive: ~2GB para PDFs

## 🛠️ Como Usar

### 1. Clone este repositório
```bash
git clone https://github.com/SEU_USUARIO/scraper-relatorios-prefeitos.git
cd scraper-relatorios-prefeitos
```

### 2. Execute o script

**No Google Colab (recomendado):**
1. Abra o notebook `scraper_relatorios_prefeitos.ipynb`
2. Conecte ao Google Drive quando solicitado
3. Execute todas as células
4. Aguarde o processamento (6-8h total)

**Localmente:**
```bash
python scraper_relatorios_prefeitos.py
```

## 📁 Estrutura do Projeto
```
scraper-relatorios-prefeitos/
├── scraper_relatorios_prefeitos.ipynb   # Notebook principal
├── scraper_relatorios_prefeitos.py      # Versão script
├── README.md                             # Este arquivo
├── requirements.txt                      # Dependências
└── examples/
    └── resultado_relatorios.csv         # Exemplo de saída
```

## 📊 Dados Extraídos

Para cada município, o script extrai:
- 💰 Saldo em conta
- 📅 Recursos Ciclo 1 (pago)
- 📅 Recursos Ciclo 2 (estimado)
- 👥 Matrículas pactuadas e declaradas
- 📍 Informações geográficas (UF, código IBGE)

## 🎨 Funcionalidades

- [x] Download automático via requisições HTTP
- [x] Salvamento incremental (retoma de onde parou)
- [x] Processamento paralelo
- [x] Log de erros e sucessos
- [x] Cache para evitar reprocessamento
- [x] Estatísticas em tempo real
- [x] Ranking automático por valores

## ⚙️ Configurações

Edite as variáveis no início do script:
```python
OUTPUT_DIR_LOCAL = "/content/relatorios_prefeitos"
DRIVE_FOLDER = "/content/drive/MyDrive/relatorios_prefeitos"
NUM_PROCESSOS = 2  # Ajuste conforme sua CPU
```

## 📈 Exemplo de Saída
```csv
municipio,uf,codigo_ibge,saldo_conta,ciclo1_pago,ciclo2_estimado,total
São Paulo,SP,3550308,12500000.00,35000000.00,25813039.56,73313039.56
Rio de Janeiro,RJ,3304557,8200000.00,22000000.00,15091708.54,45291708.54
...
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se livre para:
- 🐛 Reportar bugs
- 💡 Sugerir melhorias
- 🔧 Enviar pull requests

## 📝 Licença

MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.



---

⭐ Se este projeto te ajudou, deixe uma estrela!

**Tempo economizado: 232 horas → 8 horas = 96,6% de redução** 🚀
