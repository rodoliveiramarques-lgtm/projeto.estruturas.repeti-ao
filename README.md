Os cenários abaixo foram simulados para validar a robustez da lógica aplicada e o comportamento do programa frente a diferentes comportamentos operacionais:

 Teste 1: Validação de entradas inválidas
Descrição:** Definiu-se o limite em `40.0°C`. Foram inseridos valores inválidos e fora do escopo operacional (como `-300.0°C`).
Resultado Obtido:** O programa identificou o valor incorreto com sucesso, exibiu a mensagem *"Erro: Valor inválido inserido!"* e bloqueou o avanço do código, exigindo uma nova digitação válida do operador.

Teste 2: Temperaturas acima do limite, porém não consecutivas
Descrição:** Com limite em `50.0°C`, a sequência inserida foi: `52.0°C` (Acima), `48.0°C` (Seguro), `53.0°C` (Acima), `51.0°C` (Acima), `45.0°C` (Seguro).
Resultado Obtido:** O programa emitiu os alertas individuais de temperatura alta nos momentos corretos, mas resetou o contador de segurança sempre que uma temperatura normal foi registrada, mantendo o sistema em funcionamento sem desligamentos prematuros.

 Teste 3: Três temperaturas consecutivas acima do limite
 Descrição: Com o limite em `35.0°C`, foi digitada a sequência direta: `36.5°C` (1ª consecutiva), `38.0°C` (2ª consecutiva), `35.2°C` (3ª consecutiva).
Resultado Obtido: O sistema registrou os três alertas em sequência e disparou o protocolo de emergência imediatamente após a terceira leitura alta, exibindo a mensagem "Alerta Crítico: 3 leituras consecutivas acima do limite. Encerrando monitoramento!"* e finalizando a execução de forma segura.

