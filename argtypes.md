# Argtypes

Os argTypes no Storybook são uma forma de configurar, documentar e controlar os argumentos (props) de um componente dentro da interface interativa do Storybook.

## Em detalhes:

### 📌 O que são `args`?

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

### 🧠 E os `argTypes`?

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
