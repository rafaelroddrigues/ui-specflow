# Automation Frontend Tests - SpecFlow Selenium

O objetivo deste projeto � fornecer um bom ponto de partida para quem procura usar SpecFlow e Selenium com C# na plataforma .NET Core 3.1, demonstrando os resultados com o framework Allure Report. Tamb�m procura demonstrar uma estrutura utilizando o padr�o PageObject.

**Refer�ncias**
- [Selenium](http://www.seleniumhq.org/)
- [SpecFlow](http://specflow.org/)
- [Allure](https://docs.qameta.io/allure/)
- [Webdriver Manager](https://www.npmjs.com/package/webdriver-manager)

### Setup - Windows

Download e instale [Visual Studio](https://visualstudio.microsoft.com/) ou [Visual Studio Code](https://code.visualstudio.com/).

#### Visual Studio - Extension

Download e instale a extens�o [SpecFlow for Visual Studio 2019](https://marketplace.visualstudio.com/items?itemName=TechTalkSpecFlowTeam.SpecFlowForVisualStudio) na sua IDE.

#### Visual Studio Code - Extension

Download e instale a extens�o [.NET Core Test Explorer](https://marketplace.visualstudio.com/items?itemName=formulahendry.dotnet-test-explorer) na sua IDE.
Esta extens�o permite visualizar os testes, para isso crie o arquivo *.vscode/settings.json*, com o seguinte conte�do.

```
{
    "dotnet-test-explorer.testProjectPath": "**/**(nome do diret�rio onde est� seu projeto).csproj"
}
```

#### Instale Scoop (utilit�rio para instalar programas pela linha de comando)

**Requerimentos**
- [PowerShell 3](https://www.microsoft.com/en-us/download/details.aspx?id=34595)

Para instalar o Scoop abra o PowerShell e executa os seguintes comandos.
```
$ set-executionpolicy unrestricted -s cu
```
```
$ iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
```

#### Git

Instale o Git para conseguir clonar o projeto para sua m�quina.
```
$ scoop install git
```

### Clone

Clone o projeto.
```
$ git clone TODO
```

### Webdriver Manager

**Requerimentos**
- [Node.js](https://nodejs.org/en/)

Instale o Webdriver Manager para resolver poss�veis incompatibilidades entre o webdriver e a vers�o do browser.
```
$ npm install -g webdriver-manager
```

### Allure Report

Instale o Allure Report.

```
$ scoop install allure
```
```
$ scoop update allure
```

#### Executando Testes

**Requerimentos**
- Inicie o Selenium Server.

```
$ webdriver-manager update
```
```
$ webdriver-manager start
```

Voc� pode executar no Test Explorer da sua IDE escolhida ou via command line.

Build.
```
$ dotnet build
```

Run tests.
```
$ dotnet test
```

Entao voc� pode gerar um html report via Allure.
```
$ allure generate "allure-results-directory" -c
```
E abrir o report.
```
$ allure open "allure-report-directory"
```