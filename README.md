# task-manager-api
## Configuração do ambiente (Windows / PowerShell)

Siga estes passos para criar e ativar um ambiente virtual Python e instalar as dependências listadas em `requirements.txt`.

1. Verifique a versão do Python instalada:

```powershell
python --version
# ou, se necessário
py -3 --version
```

2. Entre na pasta do projeto (substitua pelo caminho correto):

```powershell
cd task-manager-api
```

3. Crie o ambiente virtual na pasta oculta `.venv`:

```powershell
python -m venv .venv
```

4. Ative o ambiente virtual:

- PowerShell (recomendado no Windows):

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
.\.venv\Scripts\Activate.ps1
```

- cmd.exe:

```cmd
.\.venv\Scripts\activate.bat
```

- Git Bash / WSL:

```bash
source .venv/bin/activate
```

5. Atualize o `pip` e instale as dependências (com o venv ativado):

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

6. Verifique que o venv está ativo (o prompt normalmente mostra `(.venv)`):

```powershell
python -c "import sys; print(sys.executable)"
```

O caminho retornado deve apontar para `.venv\Scripts\python.exe`.

7. Executar a aplicação (exemplo com `uvicorn`; ajuste o `module:app` conforme seu código):

```powershell
uvicorn main:app --reload --host 127.0.0.1 --port 8000
```

8. Para sair do ambiente virtual:

```powershell
deactivate
```

---

Arquivo de dependências:

As dependências estão fixadas em `requirements.txt` para garantir reprodutibilidade. Caso queira atualizar versões, modifique o arquivo e rode:

```powershell
pip install -r requirements.txt
```

