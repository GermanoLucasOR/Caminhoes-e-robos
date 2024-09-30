# Caminhoes-e-robos

Simulador de Operações de Inspeção e Transporte em um Armazém Automatizado

Descrição:

Este projeto implementa um simulador de operações de um armazém automatizado usando threads em C.
Robôs de inspeção e caminhões de transporte são representados por threads distintas, que operam de
maneira sincronizada. A inspeção de itens é realizada pelos robôs antes que eles sejam estocados,
e em seguida os caminhões transportam os itens estocados.

O programa utiliza mutexes para garantir acesso exclusivo às áreas de inspeção e transporte, e
barreiras para sincronizar o início e o término de cada rodada de inspeção e carregamento.

Funcionalidades:

1. Inspeção e Estocagem: Cada robô de inspeção inspeciona e estoca um item no armazém.
2. Carregamento: Cada caminhão carrega um item estocado, removendo-o do estoque.
3. Sincronização: A sincronização entre robôs e caminhões é feita usando barreiras, de forma que
   todos os robôs e caminhões completam uma rodada de operações antes de iniciar outra.
4. Rodadas Dinâmicas: O usuário pode definir o número de rodadas que deseja executar.

Dependências:

- Compilador GCC (ou outro compilador C compatível)
- POSIX Threads (pthread.h), que já está disponível em sistemas Unix-like (Linux e macOS).

Compilação:

Para compilar o programa, abra um terminal na pasta onde o código está localizado e execute o comando:

gcc -o simulador simulador.c -pthread

Isso irá gerar o executável `simulador`.

Execução:

Após compilar o programa, execute-o no terminal da seguinte forma:

./simulador

O programa solicitará que você insira:

1. Número de robôs de inspeção: Quantas threads de robôs de inspeção serão criadas.
2. Número de caminhões: Quantas threads de caminhões serão criadas.
3. Número de rodadas: Quantas rodadas de inspeção e carregamento devem ser executadas.

Observações:

- Comportamento não determinístico: Como o programa utiliza threads, a ordem das operações exibidas
  pode variar entre execuções devido ao agendamento das threads pelo sistema operacional.
- Simulação com sleep: O uso de `sleep` foi incluído para facilitar a visualização das operações no
  terminal, criando um atraso artificial entre as ações de inspeção e carregamento.
- Limitações: O programa não verifica limites de estoque, assumindo que os robôs de inspeção
  continuarão a inspecionar e estocar enquanto houver rodadas a serem executadas.
