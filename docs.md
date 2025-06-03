# O que é a aba "Docs" do Storybook?

A aba **"Docs"** do Storybook é uma funcionalidade que gera automaticamente uma documentação interativa para os componentes com base nas suas histórias (`.stories.tsx`), metadados e tipos. Ela permite visualizar propriedades (props), exemplos de uso e comportamento dos componentes em um formato acessível, facilitando a consulta por times de design, desenvolvimento e produto.

Essa documentação é gerada automaticamente quando se utiliza a feature chamada `autodocs`, presente a partir da versão 7 do Storybook.

### 📚 Sumário

1. [Ocultando a aba "Docs" de um componente](#ocultando-a-aba-docs-de-um-componente-no-storybook)
   - [Quando usar](#quando-usar)
   - [Observações](#observações)


## Ocultando a aba "Docs" de um componente no Storybook

Para evitar que o Storybook gere automaticamente a aba **"Docs"** para um componente, adicione a seguinte propriedade ao `export default` da sua story:

```ts
export default {
  title: 'SeuComponente/Exemplo',
  component: SeuComponente,
  tags: ['!autodocs'], // <- Isso oculta a aba Docs
};
```

### Quando usar
- Quando não quiser que a documentação automática seja exibida.
- Para componentes internos ou auxiliares que não precisam estar documentados.

### Observações
- Isso não impede você de criar uma documentação manual se quiser.
- Apenas oculta a documentação automática (autodocs) gerada pelo Storybook.
