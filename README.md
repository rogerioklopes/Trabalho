# Automação de Fluxos do Tableau Prep via Linha de Comando

Este repositório contém scripts em **batch (.bat)** para executar fluxos do Tableau Prep Builder de forma automatizada no Windows.

## Pré-requisitos

- **Tableau Prep Builder 2025.2** instalado no caminho padrão: C:\Program Files\Tableau\Tableau Prep Builder 2025.2\
- Arquivos de fluxo do Tableau Prep (`.tfl` ou `.tflx`) salvos localmente.
- Windows com acesso ao **Prompt de Comando** e permissão para executar scripts.

## Estrutura dos Scripts

Os arquivos `.bat` seguem a seguinte lógica:

1. Acessar a pasta `scripts` do Tableau Prep Builder.
2. Executar o utilitário `tableau-prep-cli.bat` apontando para o fluxo desejado.
3. Usar `pause` para manter a janela aberta após a execução.

### Exemplo: financeiro.bat

```bat
cd\
cd "Program Files\Tableau\Tableau Prep Builder 2025.2\scripts"
tableau-prep-cli.bat -t "C:\Users\Rogerio\Desktop\Prep Command line\Flows\financeiro.tfl"
pause

## Como Executar Manualmente

1. Clique duas vezes no arquivo `.bat` correspondente ao fluxo que deseja rodar.
2. Aguarde a execução do Tableau Prep CLI.
3. Verifique os arquivos de saída definidos no fluxo dentro do Tableau Prep Builder.

## Como Agendar a Execução Automática (Windows Task Scheduler)

1. Abra o **Agendador de Tarefas** no Windows (pesquise por "Agendador de Tarefas" no menu Iniciar).
2. Clique em **Criar Tarefa Básica**.
3. Dê um nome à tarefa (exemplo: `Executar Fluxo Financeiro`).
4. Escolha a frequência de execução (diária, semanal, etc.).
5. Defina o horário em que a tarefa deve rodar.
6. Na etapa **Ação**, selecione **Iniciar um Programa**.
7. Clique em **Procurar** e selecione o arquivo `.bat` correspondente.
8. Finalize a configuração.

A partir desse momento, o Windows executará automaticamente o fluxo no horário definido.

## Observações

- Certifique-se de que os fluxos possuem **etapas de saída configuradas** no Tableau Prep.
- Caso utilize conexões externas (bancos de dados, arquivos em rede), verifique se as credenciais estão salvas no fluxo.
- Para depuração, mantenha o comando `pause` no final do `.bat` para visualizar mensagens de erro.
