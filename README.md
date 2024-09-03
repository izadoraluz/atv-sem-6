# Testes de Bibliotecas de Hash (SHA-256) e Criptografia (AES-256) em Python

## 👤 **Integrante:**

- [Izadora Luz](https://www.linkedin.com/in/izadoraluz-rsn/)

## 👨‍🏫 **Professores:**

- [Renato Penha](https://www.linkedin.com/in/renato-penha/) - Professor orientador
- [Victor Hayashi](https://www.linkedin.com/in/vthayashi/) - Professor de programação

## **📝 Descrição**

Este projeto envolve a realização de testes utilizando bibliotecas de hash (SHA-256) e criptografia (AES-256) em Python. O objetivo é explorar as funcionalidades e diferenças entre SHA-256, um algoritmo de hash usado para verificar a integridade dos dados, e AES-256, um algoritmo de criptografia usado para proteger dados sensíveis. Foram realizados 10 testes diferentes, registrando os resultados em uma tabela e fornecendo uma comparação detalhada entre ambos os algoritmos.

### Método Utilizado

Para os testes, foram utilizadas duas bibliotecas em Python:

- **AES-256:** Utilizando a biblioteca `Crypto.Cipher.AES` do pacote `pycryptodome`, configurado no modo CBC (Cipher Block Chaining) com uma chave de 256 bits gerada aleatoriamente. As entradas foram criptografadas e, posteriormente, descriptografadas para verificar a precisão da criptografia.

- **SHA-256:** Utilizando a função `hashlib.sha256()` da biblioteca padrão `hashlib` para computar o hash SHA-256 de cada entrada de texto.

### Tabela de Resultados

A tabela abaixo apresenta os resultados obtidos para 10 entradas de texto diferentes:

| Input | SHA-256 Hash | AES-256 IV | AES-256 Ciphertext | AES-256 Decrypted |
|-------|--------------|------------|--------------------|-------------------|
| Hello World | a591a6d40bf420404a011733cfb7b190d62c65bf0bcda3... | zzGU7j5bScqcnRCRqrUNQQ== | pP/j6jrJvsLHvTWMa+cvpg== | Hello World |
| Pequeno | 4671fcf0c3c7d2d9aafaa1268b170bfc71b7fed0407e44... | 3izxWZqy60486I5hkuc0cA== | nYRDvZ0Lx5B6cr5lw8nncw== | Pequeno |
| Esta é uma string muito mais longa, destinada ... | 3758d6540ef58912a8d61c91288cbd0fb0d0423348e7ed... | 50uf6b1NLrDBNSwep6Gdbg== | P8MzLF+fsIQr14fcBFAGETCRLkWAzdWhhYGc/znIePsOKK... | Esta é uma string muito mais longa, destinada ... |
| Numberos12345 | 3806ac3131943dc0c75fef0ed24cc15b97cd9962b7b2d1... | ZWBjT3ERWk7vEe7VhVDegQ== | +zOPYsZUeMc2HiYVBK6pqA== | Numberos12345 |
| CaracteresEspeciais!@#$%^&*()_+-=[]{} ;':,.<>/? | 84a50309c90be22943af0adc866899680632b52a8665b3... | 8+/TS5vgPvOX4KgqtLXqig== | ebRV3L/pqEvj0AhfTK3bPMn6nUq1CoytrXAf5PLmIDgKJk... |
| Mais um testinho | 355effe4054d74096d4917cb99b63cdcbee5cc76818ce3... | jfR8vvypO5wjjibWX83yLw== | WGBEXS7JZL336XEcDZZPixOzaVSpUhJPZbt1sgO5dBg= | Mais um testinho |
| Vamos ver como isso funciona com uma mistura d... | ca2fd842aa5208f03aedfaf08ef06773fe91bd5392e5bf... | V04ANf9NtZPTXDH5e6wFdw== | VO6XeJDYQJXMKfX4na0vdD9RDpDxVg/LMOzab15zUsWaT6... | Vamos ver como isso funciona com uma mistura d... |
| Uma string muito, muito, muito, muito, muito, ... | e1e33357f7c9c614d7ff0fc85892b2db9e24fa20434d38... | iaQuOcq3NOTTC/nBDzGmYg== | Nvl7Y4YTFaT9sD+BrNsypBCFuM2Sm1D1sx6KUko5loOPyp... | Uma string muito, muito, muito, muito, muito, ... |
| 中文字符测试 | 46729408aa834345660d9d14359253030e6f2ee9bbce3a... | K09rCFWF5UWY+GoE0FnGbA== | p/T+0FVssS6622t8Utawer/C2WZ7tGX1izjXHwRfHlw= | 中文字符测试 |
| Тест на русском языке | 05f5341b93b42ecdc202f53bf55b2564fd1653ffe58c26... | xNUZA1RwDs8RWzV0ei3xEg== | 9+wHT7lNJMD6/rQrGOfyt+T+/UQPFBn0j9a7 | Тест на русском языке |

## 🔍 **Comparação entre AES-256 e SHA-256**

- **Propósito:** SHA-256 é um algoritmo de hash usado para verificar a integridade dos dados, enquanto AES-256 é um algoritmo de criptografia que protege a confidencialidade dos dados.

- **Irreversibilidade vs. Reversibilidade:** SHA-256 é irreversível, ou seja, não é possível recuperar os dados originais a partir do hash. AES-256 é reversível, permitindo a recuperação dos dados originais com a chave correta.

- **Uso:** SHA-256 é usado principalmente para validar a autenticidade dos dados, enquanto AES-256 é usado para proteger dados sensíveis contra acessos não autorizados.

A comparação dos resultados obtidos destaca as diferenças entre SHA-256 e AES-256 em termos de aplicação e funcionalidade, ilustrando como cada algoritmo atende a diferentes necessidades de segurança de dados.

## 📚 **Referências**

DAVY. *Is AES-256 the same as SHA-256?*. iToolKit, 2023. Disponível em: <https://itoolkit.co/blog/2023/08/is-aes-256-the-same-as-sha-256/>. Acesso em: 18 mar. 2024.

MILLER, Tim. *SHA vs AES: What’s the Difference?*. Tech Colleague, 2023. Disponível em: <https://techcolleague.com/sha-vs-aes/>. Acesso em: 18 mar. 2024.

GPT, Chat. *Revisão ortográfica*. 2024.
