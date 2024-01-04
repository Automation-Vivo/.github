# A2P Community space

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg"
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg"
  />
  <img
    alt="github contribution grid snake animation"
    src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg"
  />
</picture>

### 🧰 Principais Linguagens e ferramentas
<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="40px"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jupyter/jupyter-original-wordmark.svg" width="40px"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" width="40px"/>
</p>

### 📘​ Guias:
<details>
    <summary><h3>🦊​ Guia de commit semantico</h3></summary>
    
    ## build
    build: Alterações que afetam o sistema de construção ou dependências externas (escopos de exemplo: gulp, broccoli, npm);

    ## ci
    ci: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs);

    ## docs
    docs: referem-se a inclusão ou alteração somente de arquivos de documentação;

    ## feat
    feat: Tratam adições de novas funcionalidades ou de quaisquer outras novas implantações ao código;

    ## fix
    fix: Essencialmente definem o tratamento de correções de bugs;

    ## perf
    perf: Uma alteração de código que melhora o desempenho;

    ## refactor
    refactor: Tipo utilizado em quaisquer mudanças que sejam executados no código, porém não alterem a funcionalidade final da tarefa impactada;

    ## style
    exemplostyle: Alterações referentes a formatações na apresentação do código que não afetam o significado do código, como por 
    exemplo: espaço em branco, formatação, ponto e vírgula ausente etc;

    ## test
    test: Adicionando testes ausentes ou corrigindo testes existentes nos processos de testes automatizados (TDD);

    ## chore
    chore: Atualização de tarefas que não ocasionam alteração no código de produção, mas mudanças de ferramentas, mudanças de configuração e bibliotecas que realmente não entram em produção;
    
    ## env
    env: basicamente utilizado na descrição de modificações ou adições em arquivos de configuração em processos e métodos de integração contínua (CI), como parâmetros em arquivos de configuração de containers.
</details>

<details>
    <summary><h3>📚​ Python venv comandos </h3></summary>
    Antes de criar sua venv lembresse de deixala fora do projeto ou adicione-a ao seu gitignore para que não suba esses arquivo para o Git.

    ## Criar venv:
    python -m venv venv

    ## Ativar venv:
    cmd: venv\Scripts\Activate
    bash: source venv/Scripts/activate 

    ##Criar lista de bibliotecas "requirements.txt"
    pip freeze > requirements.txt

    ## Instalar bibliotecas do arquivo "requirements.txt":
    pip install -r requirements.txt
</details>
<details>
    <summary><h3>🛠️​​ Funções Genericas </h3></summary>
    """
  
      def deep_search(driver, tag, nome, show=False):
          
          list_elements = driver.find_elements(By.TAG_NAME, tag)
          for line in list_elements:
              try:
                  text_line = line.text
                  if show == True:
                      print(text_line)
              except Exception as e:
                  print('erro: ', e)
              if nome == text_line:
                  line.click(),sleep(3)
                  break
              
          return line
      
      def count_lines_table(driver, NTable):
          thead = driver.find_elements(By.TAG_NAME, 'thead')[NTable].find_element(By.XPATH, './parent::table/parent::div/parent::div/parent::div')
          nlinhas= len(thead.find_elements(By.TAG_NAME, 'tr')) -2 
          return nlinhas
      
      def search_cell(driver, NTable:int, Nrow, NColumn):
          thead = driver.find_elements(By.TAG_NAME, 'thead')[NTable].find_element(By.XPATH, './parent::table/parent::div/parent::div/parent::div')
          tbody = thead.find_elements(By.TAG_NAME,'tbody')[0].find_elements(By.TAG_NAME,'tr')[Nrow].find_elements(By.TAG_NAME,'td')[NColumn]
      
          return tbody
      
      def checked_icon(driver,Ntable, Column):
          lista_checados = []
          nlinhas = count_lines_table(driver, Ntable) + 1
          for _ in range(nlinhas):
              print(_)
              sleep(3)
              try:
                  ischeck = search_cell(driver, Ntable, _, Column).find_element(By.XPATH,'img').get_attribute('src').split("/")[-1]
                  print(ischeck,"HDGVJBFVFHJVBD")
                  if ischeck == 'check_d.gif':
                      sleep(3)
                      Column_NS = search_cell(driver, Ntable, _, 20).text
                      lista_checados.append(Column_NS)
              except Exception as e:
                  print('Image check not found',e)
                  
          return lista_checados
      
      def ordenamento_checked_icons(Column_EnviadoAtlys, Column_AtualizadoAtlys):
          sorting = []
      
          for _ in Column_EnviadoAtlys:
              if _ in Column_AtualizadoAtlys:
                  sorting.append(_)
          print(sorting)
          return sorting    
  """
</details>

### VivoCorp
👉 https://github.com/Automation-Vivo/rpa-vivocorp


### Modo de desenvolvimento e testes do VivoCorp
👉 https://github.com/Automation-Vivo/VIVOCORP_DEVMODE


