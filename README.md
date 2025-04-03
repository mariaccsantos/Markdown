# Documentação da Análise e Melhorias do Código

## Introdução
Estes documento descreve as melhorias realizadas no código original da Calculadora de Fatorial e Verificador de Número Primo.

---

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fatorial e Número Primo</title>
</head>
<body>
    <h2>Calculadora de Fatorial e Verificador de Número Primo</h2>

    <label for="numero">Digite um número:</label>
    <input type="number" id="numero">
    <button onclick="calcular()">Calcular</button>
    <p id="resultado"></p>

```
```javascript
    <script>
       // Função para calcular o fatorial de um número de forma iterativa
       function calcularFatorial(n) {
           if (n === 0 || n === 1) {
               return 1;
           }
           let resultado = 1;
           for (let i = 2; i <= n; i++) {
               resultado *= i;
           }
           return resultado;
    }

    // Função para verificar se um número é primo
    function verificarNumeroPrimo(numero) {
        if (numero <= 1) {
            return false;
        }
        // Melhorando a eficiência: verificamos apenas até a raiz quadrada do número
        for (let i = 2; i <= Math.sqrt(numero); i++) {
             if (numero % i === 0) {
                 return false;
             }
        }
        return true;
    }
    // Função principal que é acionada ao clicar no botão
    function calcular() {
        let numero = parseInt(document.getElementById("numero").value);
        
        // Validação para impedir valores negativos ou númericos
        if (isNaN(numero) || numero < 0) {
            document.getElementById("resultado").innerHTML = "Por favor, insira um número inteiro não negativo.";
            return;
        }

        let fatorial = calcularFatorial(numero);
        let primo = verificarNumeroPrimo(numero);
        
        // Exibição dos resultados na página
        document.getElementById("resultado").innerHTML =
             `O fatorial de ${numero} é ${fatorial} <br>` +
             `O número ${numero} ${primo ? "é primo." : "não é primo."}`;
        }
    </script>
</body>
</html>
```

---

# Respostas 
1. Questão
> Foram feitas melhorias significativas no código para torná-lo mais legível e eficiente. A indentação foi corrigida para facilitar a compreensão, e os comentários explicam o funcionamento de cada parte do código. A verificação de número primo foi otimizada para verificar apenas até a raiz quadrada do número, melhorando o desempenho. Além disso, foi adicionada uma validação para impedir entradas inválidas, garantindo que apenas números inteiros não negativos sejam processados.

2. Questão
> A rastreabilidade no desenvolvimento de software é essencial para garantir que as alterações no código sejam compreendidas e documentadas. Com um histórico claro de modificações, outros desenvolvedores podem facilmente entender a lógica implementada e identificar eventuais problemas. Além disso, a rastreabilidade permite acompanhar a evolução do código ao longo do tempo, tornando a manutenção mais eficiente e reduzindo a necessidade de reescrever grandes partes do sistema.

3. Questão
>Um código bem documentado segue boas práticas que tornam sua manutenção e expansão mais fáceis. Algumas dessas práticas incluem:
- **Nomes descritivos para variáveis e funções**, facilitando a compreensão de sua finalidade.
- **Uso de comentários explicativos**, ajudando desenvolvedores a entenderem rapidamente o propósito de cada trecho do código.
- **Organização e padronização do código**, garantindo uma estrutura clara e de fácil navegação.
- **Validações e tratamento de erros**, evitando falhas inesperadas e melhorando a robustez do sistema.

4. Questão
>O Markdown é uma ferramenta essencial para a documentação de código, pois permite a criação de documentos bem formatados e legíveis sem a complexidade de editores mais sofisticados. Ele é amplamente utilizado em plataformas como GitHub, GitLab e outros repositórios de código, tornando a comunicação entre desenvolvedores mais eficiente. Além disso, a simplicidade do Markdown facilita a escrita e a atualização da documentação, garantindo que ela se mantenha relevante ao longo do tempo.

5. Questão
>A adoção de padrões e boas práticas no desenvolvimento de software é fundamental para garantir que o código possa ser facilmente mantido e escalado. Um código bem estruturado permite que novos desenvolvedores compreendam rapidamente sua lógica e contribuam para melhorias sem comprometer a funcionalidade existente. Além disso, sistemas bem organizados reduzem a ocorrência de bugs e facilitam a adição de novas funcionalidades sem gerar conflitos com o código já implementado.

