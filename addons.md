# Addons

Os addons do Storybook são ferramentas que estendem as funcionalidades do Storybook, permitindo personalizar e melhorar a experiência de desenvolvimento de componentes. Eles ajudam a integrar funcionalidades adicionais, como documentação, testes, acessibilidade, e muito mais.

## Exemplos de Addons Populares

1. **@storybook/addon-actions**  
   Permite registrar eventos e interações de componentes para facilitar o rastreamento de ações.

2. **@storybook/addon-a11y**  
   Ajuda a verificar a acessibilidade dos componentes, fornecendo relatórios e sugestões.

3. **@storybook/addon-docs**  
   Gera automaticamente documentação para os componentes com base em seus metadados.

## Como Adicionar um Addon

1. Instale o addon desejado via npm ou yarn:
   ```bash
   npm install @storybook/addon-actions --save-dev
   ```
2. Adicione o addon ao arquivo `main.js` na configuração do Storybook:
   ```javascript
   module.exports = {
     addons: ["@storybook/addon-actions"],
   };
   ```

## Criando Addons Personalizados

Se nenhum addon existente atender às suas necessidades, você pode criar um addon personalizado. A documentação oficial do Storybook fornece um guia detalhado para isso.

Para mais informações, consulte a [documentação oficial dos addons do Storybook](https://storybook.js.org/docs/react/addons/introduction).
