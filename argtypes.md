# Argtypes

Os argTypes no Storybook são uma forma de configurar, documentar e controlar os argumentos (props) de um componente dentro da interface interativa do Storybook.

### Sumário

- [Em detalhes](#em-detalhes)
  - [O que são `args`?](#o-que-são-args)
  - [O que são `argTypes`?](#o-que-são-argtypes)
- [Ordenação por ordem alfabética](#ordenação-por-ordem-alfabética)
- [Como adicionar defaultValue na tabela de documentação](#como-adicionar-defaultvalue-na-tabela-de-documentação)

## Em detalhes

### O que são `args`?

Os args são os valores das props que você passa para um componente nas suas stories.

Exemplo:

```javascript
export const Padrao = {
  args: {
    label: "Clique aqui",
    disabled: false,
  },
};
```

Isso equivale a `<Botao label="Clique aqui" disabled={false} />`.

### O que são `argTypes`?

São metadados que descrevem os args — tipo, descrição, controle, categoria, ordem, etc. Isso é útil tanto para gerar documentação automática quanto para permitir a edição desses valores via painel de controles do Storybook.

Exemplo de argTypes:

```javascript
argTypes: {
    label: {
        description: 'Texto exibido no botão',
        control: 'text' ,
    },
    disabled: {
        description: 'Desativa o botão',
        control: 'boolean',
    },
}
```

Com isso, o Storybook vai:

- Mostrar essas props no painel de documentação (Docs tab).
- Permitir que o usuário altere elas interativamente no painel de controles (`Controls` tab).
- Categorizar ou ordenar essas props, se você quiser.

## Ordenação por ordem alfabética

Você pode ordenar os argTypes por ordem alfabética usando a opção parameters dentro do default export da sua história. A chave para isso é usar `sort: 'alpha'` dentro de controls.

Aqui está um exemplo de como fazer isso:

```javascript
import type { Meta, StoryObj } from "@storybook/react";
import { MeuComponente } from "./MeuComponente";

const meta: Meta<typeof MeuComponente> = {
  title: "Componentes/MeuComponente",
  component: MeuComponente,
  parameters: {
    controls: {
      sort: "alpha",
    },
  },
};

export default meta;
type Story = StoryObj<typeof MeuComponente>;

export const Padrao: Story = {
  args: {
    // seus args aqui
  },
};
```

## Como adicionar defaultValue na tabela de documentação

Se quiser exibir o valor padrão de uma prop na tabela da aba "Docs" do Storybook, use a chave table.defaultValue dentro da configuração de argTypes. Isso não afeta o valor usado nos controles, apenas documenta.

Exemplo:

```javascript
argTypes: {
  label: {
    description: 'Texto exibido no botão',
    control: 'text',
    table: {
      defaultValue: { summary: 'Clique aqui' },
    },
  },
  disabled: {
    description: 'Desativa o botão',
    control: 'boolean',
    table: {
      defaultValue: { summary: false },
    },
  },
}
```
> Dica: Use summary para mostrar uma string simples. Se quiser, pode usar detail para complementar com uma explicação mais longa ou com o tipo completo.

Se quiser que o valor padrão também seja usado no controle interativo do Storybook, defina em paralelo o args:

```javascript
export const Padrao = {
  args: {
    label: 'Clique aqui',
    disabled: false,
  },
};
```
Ou seja:
- `args` → define o valor inicial usado nos controles.
- `argTypes.table.defaultValue` → documenta o valor padrão na aba Docs.

Separando bem essas responsabilidades, a documentação fica clara e o comportamento interativo do componente é consistente.
