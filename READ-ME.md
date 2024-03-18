Olá! Eu realizei testes (10 como diz o barema :)) utilizando bibliotecas de hash (SHA-256) e criptografia (AES-256) em Python, resultando em 10 execuções distintas com diferentes entradas de texto. Aqui está uma descrição detalhada do método utilizado e uma comparação entre AES-256 e SHA-256 baseada nos resultados.

### Método Utilizado

Para a **criptografia AES-256**, utilizei a biblioteca `Crypto.Cipher.AES` do pacote `pycryptodome`, configurando-a para o modo CBC (Cipher Block Chaining) com uma chave de 256 bits gerada aleatoriamente. A entrada foi então criptografada (e posteriormente descriptografada) usando esta chave.

Para o **hashing SHA-256**, recusei a função `hashlib.sha256()` da biblioteca padrão `hashlib`, que utilizamos na aula de mineração com python, que computa o hash SHA-256 de uma entrada dada.

A tabela a seguir mostra os resultados obtidos para 10 entradas de texto diferentes. Para cada entrada, é fornecido o hash SHA-256, os dados criptografados com AES-256 (incluindo o vetor de inicialização IV e o texto cifrado CT), e a versão descriptografada para verificar a precisão da criptografia.

|  | Input | SHA-256 Hash | AES-256 IV | AES-256 Ciphertext | AES-256 Decrypted |
| --- | --- | --- | --- | --- | --- |
| 0 | Hello World | a591a6d40bf420404a011733cfb7b190d62c65bf0bcda3... | zzGU7j5bScqcnRCRqrUNQQ== | pP/j6jrJvsLHvTWMa+cvpg== | Hello World |
| 1 | Pequeno | 4671fcf0c3c7d2d9aafaa1268b170bfc71b7fed0407e44... | 3izxWZqy60486I5hkuc0cA== | nYRDvZ0Lx5B6cr5lw8nncw== | Pequeno |
| 2 | Esta é uma string muito mais longa, destinada ... | 3758d6540ef58912a8d61c91288cbd0fb0d0423348e7ed... | 50uf6b1NLrDBNSwep6Gdbg== | P8MzLF+fsIQr14fcBFAGETCRLkWAzdWhhYGc/znIePsOKK... | Esta é uma string muito mais longa, destinada ... |
| 3 | Numberos12345 | 3806ac3131943dc0c75fef0ed24cc15b97cd9962b7b2d1... | ZWBjT3ERWk7vEe7VhVDegQ== | +zOPYsZUeMc2HiYVBK6pqA== | Numberos12345 |
| 4 | CaracteresEspeciais!@#$%^&*()_+-=[]{}|;':,.<>/? | 84a50309c90be22943af0adc866899680632b52a8665b3... | 8+/TS5vgPvOX4KgqtLXqig== | ebRV3L/pqEvj0AhfTK3bPMn6nUq1CoytrXAf5PLmIDgKJk... | CaracteresEspeciais!@#$%^&*()_+-=[]{}|;':,.<>/? |
| 5 | Mais um testinho | 355effe4054d74096d4917cb99b63cdcbee5cc76818ce3... | jfR8vvypO5wjjibWX83yLw== | WGBEXS7JZL336XEcDZZPixOzaVSpUhJPZbt1sgO5dBg= | Mais um testinho |
| 6 | Vamos ver como isso funciona com uma mistura d... | ca2fd842aa5208f03aedfaf08ef06773fe91bd5392e5bf... | V04ANf9NtZPTXDH5e6wFdw== | VO6XeJDYQJXMKfX4na0vdD9RDpDxVg/LMOzab15zUsWaT6... | Vamos ver como isso funciona com uma mistura d... |
| 7 | Uma string muito, muito, muito, muito, muito, ... | e1e33357f7c9c614d7ff0fc85892b2db9e24fa20434d38... | iaQuOcq3NOTTC/nBDzGmYg== | Nvl7Y4YTFaT9sD+BrNsypBCFuM2Sm1D1sx6KUko5loOPyp... | Uma string muito, muito, muito, muito, muito, ... |
| 8 | 中文字符测试 | 46729408aa834345660d9d14359253030e6f2ee9bbce3a... | K09rCFWF5UWY+GoE0FnGbA== | p/T+0FVssS6622t8Utawer/C2WZ7tGX1izjXHwRfHlw= | 中文字符测试 |
| 9 | Тест на русском языке | 05f5341b93b42ecdc202f53bf55b2564fd1653ffe58c26... | xNUZA1RwDs8RWzV0ei3xEg== | 9+wHT7lNJMD6/rQrGOfyt+T+/UQPFBn0j9a7 | Тест на русском языке |

### Comparação entre AES-256 e SHA-256

- **Propósito**: SHA-256 é um algoritmo de hash que transforma dados de entrada em uma string de tamanho fixo, ideal para verificar a integridade dos dados. AES-256, por outro lado, é um algoritmo de criptografia que permite a encriptação e decriptação de dados, mantendo a confidencialidade da informação.

- **Irreversibilidade vs. Reversibilidade**: O hash SHA-256 é unidirecional, significando que não se pode obter os dados originais a partir do hash. AES-256 é reversível, permitindo a recuperação dos dados originais com a chave correta.

- **Uso**: SHA-256 é comumente usado em aplicações de segurança para validar a autenticidade dos dados. AES-256 é utilizado para proteger dados sensíveis contra acessos não autorizados, garantindo que apenas indivíduos com a chave correta possam acessar a informação original.

Os resultados obtidos oferecem uma visão das diferenças funcionais e de propósito entre SHA-256 e AES-256, refletindo suas aplicações específicas em segurança de dados. Enquanto cada hash SHA-256 gerado é único e irreversível, garantindo assim a integridade e a autenticidade dos dados sem revelar sua essência, a criptografia AES-256 destaca-se pela capacidade de salvaguardar a confidencialidade dos dados, permitindo a recuperação exata da informação original com o uso da chave correta. Essa dualidade entre a irreversibilidade do SHA-256 e a reversibilidade segura do AES-256 ilustra a complementaridade dos dois métodos em um espectro de segurança de dados, onde um foca na proteção da informação contra alterações indetectáveis e o outro na sua proteção contra acessos não autorizados.

A análise baseada nos resultados obtidos não apenas confirma a importância de selecionar o algoritmo apropriado conforme o requisito de segurança—integridade versus confidencialidade—mas também sublinha a robustez dessas tecnologias em seus respectivos domínios. O SHA-256, com sua função de hash unidirecional, serve como um mecanismo de verificação de integridade eficaz, crucial para sistemas de verificação de dados como blockchain e certificados digitais, onde a autenticidade precisa ser garantida sem necessariamente ocultar a informação. Por outro lado, o AES-256, com sua capacidade de criptografia e descriptografia, é indispensável para a proteção de dados sensíveis em trânsito e em repouso, desde comunicações seguras até armazenamento de dados.

fontes:

1. https://itoolkit.co/blog/2023/08/is-aes-256-the-same-as-sha-256/

2. https://techcolleague.com/sha-vs-aes/

3. Chat Gpt - revisão ortográfica