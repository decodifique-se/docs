# ADR 001: Escolha de Next.js para Site Estático no GitHub Pages

## Contexto

Queremos criar um site estático para a organização, hospedado no GitHub Pages. O objetivo é ter uma página institucional e de documentação dos projetos da organização, acessível publicamente em `<orgname>.github.io`. Avaliamos várias opções, incluindo Next.js, Jekyll, Hugo e sites HTML/CSS tradicionais.

### Requisitos para o Site

1. **Escalabilidade e Facilidade de Manutenção**: O site deve ser fácil de atualizar e capaz de evoluir para suportar conteúdos adicionais ou novas funcionalidades, caso o escopo aumente no futuro.
2. **SEO e Desempenho**: O site deve carregar rapidamente e ser amigável para SEO, uma vez que será uma porta de entrada pública para a organização.
3. **Compatibilidade com GitHub Pages**: A ferramenta deve ser compatível com GitHub Pages e suportar deploys automatizados.
4. **Comunidade e Suporte**: A tecnologia deve ter uma comunidade ativa e uma boa documentação, garantindo facilidade de suporte.

## Opções Consideradas

1. **Next.js**: Um framework React moderno que oferece geração de sites estáticos e suporte a funcionalidades dinâmicas, se necessário.
2. **Jekyll**: Um gerador de site estático baseado em Ruby, bem suportado pelo GitHub Pages e popular para sites de documentação.
3. **Hugo**: Um gerador de site estático em Go, conhecido pela velocidade e flexibilidade.
4. **HTML/CSS Tradicional**: Criar um site puramente estático com HTML e CSS, sem frameworks.

## Decisão

Escolhemos **Next.js** para desenvolver o site estático da organização no GitHub Pages.

## Justificativas

1. **Escalabilidade e Evolução**:
   - Next.js oferece uma estrutura escalável que facilita o desenvolvimento inicial e, ao mesmo tempo, permite a adição de funcionalidades dinâmicas (APIs, SSR) no futuro, caso o site evolua para uma aplicação mais complexa.
   - Diferente de Jekyll e Hugo, Next.js é baseado em JavaScript/React, o que proporciona um ambiente moderno e alinhado com o ecossistema de frontend em evolução.

2. **SEO e Desempenho**:
   - Com a capacidade de gerar sites estáticos, Next.js garante um excelente desempenho para as páginas, enquanto suas ferramentas de SEO ajudam a melhorar a visibilidade em mecanismos de busca.
   - O Next.js permite a configuração de otimizações como imagens e roteamento dinâmico, garantindo uma experiência rápida e responsiva.

3. **Integração e Compatibilidade com GitHub Pages**:
   - Next.js é facilmente exportável como um site estático (`next export`), o que o torna compatível com GitHub Pages.
   - A estrutura de exportação do Next.js cria um diretório `out/` com arquivos HTML estáticos, ideal para deploys simples no GitHub Pages.

4. **Comunidade e Suporte**:
   - Next.js é amplamente usado e possui uma grande comunidade, oferecendo suporte robusto e uma vasta documentação.
   - A popularidade do Next.js significa que muitos desenvolvedores têm experiência com ele, facilitando a manutenção e onboarding de novos contribuidores.

5. **Automação e Deploy**:
   - Next.js permite integração com GitHub Actions para automação de deploys no GitHub Pages, simplificando o fluxo de trabalho e reduzindo o esforço de manutenção.

## Consequências

1. **Adoção de Next.js**: Precisaremos configurar a exportação estática do Next.js e ajustar o projeto para que seja adequado ao GitHub Pages.
2. **Familiaridade com React**: Os desenvolvedores que contribuírem para o site precisarão de conhecimento em React/JavaScript, o que poderá exigir aprendizado adicional para membros que não estão familiarizados com essa stack.
3. **Automatização do Deploy**: Será configurado um pipeline de GitHub Actions para automatizar o deploy do site para o GitHub Pages sempre que uma nova atualização for feita na branch principal.

---

Esse ADR documenta nossa escolha de Next.js e fornece uma referência clara para futuras decisões de arquitetura. Qualquer ajuste ou revisão pode ser registrado em novos ADRs se houver uma mudança de contexto ou requisitos.