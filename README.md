# desafio_target_sistemas
 
## Questão 1:
Resposta: 78

## Questão 2:
a) 9
b) 128
c) 49
d) 100
e) 13
f) 20

## Questão 3:
(Utilizei a linguagem Dart)
``` dart
void calcularFaturamento(List<double> faturamentos) {
  double menorFaturamento = double.infinity;
  double maiorFaturamento = 0;
  double somaFaturamento = 0;
  int diasComFaturamento = 0;

  for (double faturamento in faturamentos) {
    if (faturamento > 0) {
      if (faturamento < menorFaturamento) {
        menorFaturamento = faturamento;
      }
      if (faturamento > maiorFaturamento) {
        maiorFaturamento = faturamento;
      }
      somaFaturamento += faturamento;
      diasComFaturamento++;
    }
  }
```

  double mediaAnual = somaFaturamento / diasComFaturamento;
  int diasAcimaDaMedia = faturamentos.where((f) => f > mediaAnual).length;

  print("Menor Faturamento: $menorFaturamento");
  print("Maior Faturamento: $maiorFaturamento");
  print("Dias com faturamento acima da média: $diasAcimaDaMedia");
}

void main() {
  List<double> faturamentos = [/* valores de faturamento diário */];
  calcularFaturamento(faturamentos);
}

## Questão 4:

Modelo lógico do banco de dados

Tabelas:
- Clientes
    - id_cliente (PK)
    - razao_social
    - estado (FK para tabela Estados)

- Telefones
    -id_telefone (PK)
    - id_cliente (FK)
    - numero
    - tipo_telefone (FK para tabela TiposTelefone)

- TiposTelefone
    - id_tipo (PK)
    - descricao

- Estados
    - id_estado (PK)
    - sigla_estado

Consulta SQL
``` sql
SELECT c.id_cliente, c.razao_social, t.numero 
FROM Clientes c
JOIN Telefones t ON c.id_cliente = t.id_cliente
JOIN Estados e ON c.estado = e.id_estado
WHERE e.sigla_estado = 'SP';
```

## Questão 5:
O caminhão estará mais próximo de Ribeirão Preto.

Explicação:
Distância total: 125 km
Velocidade do carro: 90 km/h
Velocidade do caminhão: 80 km/h
O carro leva um atraso de 3x5 = 15 minutos

Como o carro e o caminhão se movem em direção um ao outro, a velocidade relativa deles é:
VR = 90 + 80 = 170 km/h => 0.735 => 44

Eles se encontrarão após 44 minutos.

Como o tempo até o encontro (44 minutos) é menor do que o tempo necessário para o carro compensar seu atraso (15 minutos), o carro estará mais lento durante o percurso.
