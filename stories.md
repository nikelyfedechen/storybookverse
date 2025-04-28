# Como Inserir Descrição nas Variações do Componente

No Storybook, você pode adicionar uma descrição detalhada a cada **variação do componente** utilizando a chave `parameters.docs.description.story`. Isso é útil para fornecer contexto adicional sobre como e quando usar determinada variação de um componente, garantindo que desenvolvedores e designers compreendam melhor o seu uso.

### Exemplo de Inserção de Descrição

Abaixo está um exemplo de como adicionar uma descrição em uma **variação do componente** no Storybook:

```tsx
export const ErrorState: Story = {
  parameters: {
    docs: {
      description: {
        story:
          "O `InputField` no estado de erro é utilizado para indicar que a entrada fornecida não é válida ou que há um problema com os dados inseridos. Este estado é visualmente destacado para guiar o usuário na correção da informação.",
      },
    },
  },
  args: {
    label: "E-mail",
    value: "",
    error: "Por favor, insira um e-mail válido.",
  },
  render: (args) => <InputField {...args} />,
};
```
### Quando Usar
- Utilize essa abordagem sempre que precisar explicar as variações de um componente no Storybook, principalmente se a variação tiver comportamentos específicos ou configurações que podem causar dúvidas entre os desenvolvedores.
- A descrição ajuda a fornecer contexto e a esclarecer como e quando usar determinada variação do componente.
