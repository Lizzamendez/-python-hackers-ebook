🐍 Python Hackers: Dominando Automações
💡 Introdução — O poder das automações

Imagine eliminar tarefas repetitivas com apenas alguns comandos.
Mover arquivos, renomear planilhas, enviar e-mails automáticos, capturar dados da web — tudo isso é possível com Python, uma das linguagens mais poderosas e acessíveis do mundo.

Neste eBook, você aprenderá a pensar como um Python Hacker — alguém que usa código para resolver problemas de forma criativa e eficiente.
O objetivo não é apenas aprender a programar, mas criar soluções que economizam tempo e energia, liberando você para focar no que realmente importa.

Ao final desta leitura, você será capaz de construir suas próprias automações e dar os primeiros passos no mundo da inteligência artificial e dos bots.
🧰 Capítulo 1 — Preparando o ambiente Hacker

Antes de começar, precisamos montar o nosso “laboratório hacker”.

🐍 Instalando o Python

Acesse https://www.python.org/downloads/

Baixe a versão mais recente (recomendada).

Durante a instalação, marque a opção “Add Python to PATH”.

Verifique se deu tudo certo:
python --version
🧱 Instalando bibliotecas úteis

As automações ficam mais poderosas com bibliotecas externas.
Execute no terminal:

pip install requests beautifulsoup4 pyautogui pandas openpyxl


Essas bibliotecas permitirão:

requests → acessar APIs e sites
beautifulsoup4 → fazer web scraping
pyautogui → automatizar o mouse e o teclado
pandas/openpyxl → lidar com planilhas e dados

⚙️ Capítulo 2 — Scripts Ninja: Automatizando tarefas do dia a dia

Comece com automações simples que resolvem problemas reais.

🗂️ Organizando arquivos automaticamente
import os, shutil

pasta = "C:/Users/Lizza/Downloads"
destinos = {
    "Imagens": [".png", ".jpg"],
    "Documentos": [".pdf", ".docx", ".txt"],
    "Planilhas": [".xlsx", ".csv"],
}

for arquivo in os.listdir(pasta):
    nome, ext = os.path.splitext(arquivo)
    for pasta_destino, extensoes in destinos.items():
        if ext in extensoes:
            nova_pasta = os.path.join(pasta, pasta_destino)
            os.makedirs(nova_pasta, exist_ok=True)
            shutil.move(os.path.join(pasta, arquivo), os.path.join(nova_pasta, arquivo))
✅ O que faz:
Move automaticamente os arquivos para pastas com base na extensão.

✉️ Enviando e-mails automáticos
import smtplib
from email.mime.text import MIMEText

msg = MIMEText("Olá! Este é um e-mail enviado por um script Python Hacker 😎")
msg["Subject"] = "Automação com Python"
msg["From"] = "seuemail@gmail.com"
msg["To"] = "destinatario@gmail.com"

with smtplib.SMTP_SSL("smtp.gmail.com", 465) as smtp:
    smtp.login("seuemail@gmail.com", "sua_senha_de_aplicativo")
    smtp.send_message(msg)
💡 Use senhas de aplicativo no Gmail para autenticar com segurança.

🌐 Capítulo 3 — Domine a Web: Web Scraping e APIs
🔍 Capturando dados de sites
import requests
from bs4 import BeautifulSoup

url = "https://quotes.toscrape.com/"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

for quote in soup.find_all("span", class_="text"):
    print(quote.text)
✅ O que faz:
Extrai frases inspiradoras de um site público e imprime no terminal.

🌎 Usando APIs para obter dados
import requests

res = requests.get("https://api.coindesk.com/v1/bpi/currentprice.json")
data = res.json()

print("💰 Bitcoin agora:", data["bpi"]["USD"]["rate"], "USD")
🗃️ Capítulo 4 — Automatizando arquivos e planilhas

Você também pode automatizar relatórios e planilhas com Pandas:
import pandas as pd

vendas = pd.read_excel("vendas.xlsx")
relatorio = vendas.groupby("Vendedor")["Valor"].sum().reset_index()
relatorio.to_excel("relatorio_final.xlsx", index=False)

print("Relatório gerado com sucesso! 📊")
🤖 Capítulo 5 — Bots e automações inteligentes
⌨️ Controlando o computador com PyAutoGUI
import pyautogui
import time

time.sleep(3)
pyautogui.press('win')
pyautogui.write('chrome')
pyautogui.press('enter')
✅ O que faz:
Abre o navegador automaticamente — útil para rotinas ou bots simples.

🚀 Capítulo 6 — O próximo nível: automações com IA

O próximo passo dos Python Hackers é integrar automações com inteligência artificial.
Com bibliotecas como openai, transformers e langchain, é possível criar assistentes pessoais, gerar relatórios automáticos ou até automatizar a tomada de decisões.

“O verdadeiro poder do código está em liberar tempo para pensar.”
🧠 Conclusão

Você agora tem as ferramentas para se tornar um Python Hacker.
Com pequenas doses de curiosidade e criatividade, pode automatizar qualquer tarefa — do Excel ao navegador.

A automação é mais do que código: é liberdade digital.
E lembre-se: um verdadeiro hacker não quebra sistemas, ele os entende para melhorá-los.
📚 Recursos extras

Documentação oficial do Python

Automate the Boring Stuff with Python

Repositório de Felipe Aguiar (Desafio DIO)

✨ Criado por: Lizza Mendez
📅 Projeto desenvolvido como parte do desafio DIO: Criação de eBook com IA
