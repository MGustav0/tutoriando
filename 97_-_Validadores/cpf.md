# Validador CPF

````ts
export default function cpfValidation(value) {
  if (!value) return false

  // Aceita receber o valor como string, número ou array com todos os dígitos
  const validTypes =
    typeof value === 'string' || Number.isInteger(value) || Array.isArray(value)

  // Elimina valores com formato inválido
  if (!validTypes) return false

  // Guarda todos os dígitos em um array
  const numbers = value.toString().match(/\d/g).map(Number)

  // Valida quantidade de dígitos
  if (numbers.length !== 11) return false

  // Elimina valores inválidos com todos os dígitos repetidos
  const items = [...new Set(numbers)]
  if (items.length === 1) return false

  // Separa número base do dígito verificador
  const base = numbers.slice(0, 9)
  const digits = numbers.slice(9)

  // Cálculo base
  const calc = (n, i, x) => n * (x - i)
  
  // Utilitário de soma
  const sum = (r, n) => r + n
  
  // Cálculo de dígito verificador
  const digit = (n) => {
    const rest = n % numbers.length
    return rest < 2 ? 0 : numbers.length - rest
  }

  // Cálculo sobre o número base
  const calc0 = base.map((n, i) => calc(n, i, numbers.length - 1)).reduce(sum, 0)
  // 1o. dígito verificador
  const digit0 = digit(calc0)

  // Valida 1o. digito verificador
  if (digit0 !== digits[0]) return false

  // Cálculo sobre o número base + 1o. dígito verificador
  const calc1 = base
    .concat(digit0)
    .map((n, i) => calc(n, i, numbers.length))
    .reduce(sum, 0)
  // 2o. dígito verificador
  const digit1 = digit(calc1)

  // Valida 2o. dígito verificador
  return digit1 === digits[1]
}
````
