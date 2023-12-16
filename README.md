# Entendendo um Ransomware na Prática com Python

## Resumidamente: o que é Ransomware?
É um tipo de malware de sequestro de dados, feito por meio de criptografia, que usa como refém arquivos pessoais da própria vítima e cobra resgate para reestabelecer o acesso a estes arquivos.

## O que foi feito nesse projeto?

Primeiro, foi criado um arquivo txt que vai ser encriptado e posteriormente desencriptado.

Também aprendemos como criar o arquivo de encriptação e o de desencriptação.

É necessários usar as bibliotecas: **OS** e **Pyaes** (que é a biblioteca do Python de criptografia).

Na hora de definir a chave de encriptação, nós temos alguns modos de operação para o padrão AES (**Neste código foi usado o CTR**):
- **ECB (Electronic CodeBook)**:
  - No modo ECB, cada bloco de texto plano é cifrado independentemente um do outro. Isso significa que os mesmos blocos de texto plano sempre resultarão nos mesmos blocos cifrados.
  - Embora seja simples de entender e implementar, o modo ECB não é seguro para todos os tipos de dados, especialmente quando há padrões repetitivos no texto plano.
- **CBC (Cipher Block Chaining)**:
  - No modo CBC, cada bloco de texto plano é XORed com o bloco cifrado anterior antes de ser cifrado. Isso adiciona uma camada de dependência entre os blocos, tornando a cifra mais segura do que o modo ECB.
  - O CBC requer um vetor de inicialização (IV) para iniciar o processo de encadeamento. O IV deve ser conhecido pelo destinatário para decifrar os dados corretamente.
- **CFB (Cipher Feedback)**:
  - No modo CFB, o bloco cifrado anterior é usado para cifrar o próximo bloco de texto plano. Isso cria um fluxo contínuo de blocos cifrados.
- **CTR (Counter)**:
  - No modo CTR, um contador é usado para gerar uma sequência de blocos de chave, que são então XORed com o texto plano.
- **OFB (Output Feedback)**:
  - No modo OFB, a cifra é usada para criar uma sequência de blocos pseudoaleatórios, que são XORed com o texto plano.

![Arquivo criptografado](image.png)
![Arquivo descriptografado](image.png)