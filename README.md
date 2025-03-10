# Entrega Desafio
## DIO - Trilha .NET - Explorando a linguagem C#
## Descrição
A classe Reserva gerencia informações sobre uma reserva de hospedagem, incluindo a lista de hóspedes, a suite reservada e a quantidade de dias reservados. Também inclui métodos para cadastrar hóspedes, cadastrar uma suite, obter a quantidade de hóspedes e calcular o valor total da diária com desconto.

## Métodos

### `void CadastrarHospedes(List<Pessoa> hospedes)`
```csharp
public void CadastrarHospedes(List<Pessoa> hospedes)
{
    if (hospedes.Count <= Suite.Capacidade)
    {
        Hospedes = hospedes;
    }
    else
    {
        throw new Exception("Capacidade menor que o número de hóspedes.");
    }
}
```
- **Descrição:**
  - Registra a lista de hóspedes na reserva, garantindo que a quantidade não ultrapasse a capacidade da suite.
- **Parâmetros:**
  - `hospedes`: Lista de hóspedes a serem cadastrados.
- **Exceção:**
  - `Exception`: "Capacidade menor que o número de hóspedes."

### `void CadastrarSuite(Suite suite)`
```csharp
public void CadastrarSuite(Suite suite)
{
    Suite = suite;
}
```
- **Descrição:**
  - Atribui uma suite à reserva.
- **Parâmetros:**
  - `suite`: Objeto da classe `Suite` a ser cadastrado.

### `int ObterQuantidadeHospedes()`
```csharp
public int ObterQuantidadeHospedes()
{
    return Hospedes.Count;
}
```
- **Descrição:**
  - Retorna a quantidade de hóspedes cadastrados na reserva.
- **Retorno:**
  - Quantidade de hóspedes cadastrados na propriedade `Hospedes`.

### `decimal CalcularValorDiaria()`
```csharp
public decimal CalcularValorDiaria()
{
    decimal valor = Suite.ValorDiaria * DiasReservados;
    if (DiasReservados >= 10)
    {
        decimal desconto = valor * 0.10M;
        return valor - desconto;
    }
    return valor;
}
```
- **Descrição:**
  - Calcula o valor total da diária com base na quantidade de dias reservados e no valor da diária da suite.
  - Se a reserva for para 10 dias ou mais, um desconto de 10% é aplicado ao total.
- **Retorno:**
  - Valor total da diária após a aplicação do desconto (se aplicável).

---
# DIO - Trilha .NET - Explorando a linguagem C#
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de explorando a linguagem C#, da trilha .NET da DIO.

## Contexto
Você foi contratado para construir um sistema de hospedagem, que será usado para realizar uma reserva em um hotel. Você precisará usar a classe Pessoa, que representa o hóspede, a classe Suíte, e a classe Reserva, que fará um relacionamento entre ambos.

O seu programa deverá cálcular corretamente os valores dos métodos da classe Reserva, que precisará trazer a quantidade de hóspedes e o valor da diária, concedendo um desconto de 10% para caso a reserva seja para um período maior que 10 dias.

## Regras e validações
1. Não deve ser possível realizar uma reserva de uma suíte com capacidade menor do que a quantidade de hóspedes. Exemplo: Se é uma suíte capaz de hospedar 2 pessoas, então ao passar 3 hóspedes deverá retornar uma exception.
2. O método ObterQuantidadeHospedes da classe Reserva deverá retornar a quantidade total de hóspedes, enquanto que o método CalcularValorDiaria deverá retornar o valor da diária (Dias reservados x valor da diária).
3. Caso seja feita uma reserva igual ou maior que 10 dias, deverá ser concedido um desconto de 10% no valor da diária.


![Diagrama de classe estacionamento](diagrama_classe_hotel.png)

## Solução
O código está pela metade, e você deverá dar continuidade obedecendo as regras descritas acima, para que no final, tenhamos um programa funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.
