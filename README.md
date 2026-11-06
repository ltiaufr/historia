# História — acervo fotográfico

Protótipo inicial do site público e do cadastramento experimental.

## Arquitetura planejada

- **GitHub Pages:** galeria pública, miniaturas otimizadas e índice JSON para pesquisa local.
- **Google Drive:** fotografias originais (integração ainda **não implementada**).
- **Google Apps Script:** futuramente receberá cadastros por colaboradores autorizados e atualizará o catálogo; requer implantação, revisão de permissões e autenticação segura.

## Publicar no GitHub Pages

Em **Settings → Pages**, escolha **Deploy from a branch**, branch **main** e pasta **/(root)**; salve. Aguarde o GitHub indicar a URL publicada. Para o repositório `ltiaufr/historia`, o endereço esperado após ativação é https://ltiaufr.github.io/historia/ (verifique se a publicação realmente ocorreu).

## Testar

1. Abra a galeria publicada e pesquise por `exemplo` ou `1980`.
2. Abra `/admin/` para preencher metadados e gerar o JSON de um registro. **Não há autenticação ou upload.** Não use este formulário para dados sensíveis.
3. Substitua os registros de `dados/acervo.json` por metadados revisados. Preencha `miniatura` e `original` com URLs públicas HTTP(S) válidas. As fotos originais no Drive ainda precisam ter seu modo de entrega avaliado.
4. Teste em computador e celular.

## Estrutura de um registro

```json
{"id":"foto-001","titulo":"Praça central","descricao":"Vista histórica","local":"Cidade","ano":"1975","autor":"Acervo","palavras_chave":["praça","urbano"],"miniatura":"https://exemplo.org/miniatura.jpg","original":"https://exemplo.org/original.jpg"}
```

## Observações de segurança

Como o GitHub Pages é público, **não coloque senhas, tokens do GitHub, credenciais do Google, planilhas privadas ou imagens sem autorização neste repositório**. Um formulário HTML público não pode proteger o acesso administrativo por si só. O cadastro definitivo será publicado somente após implantação de backend com controle de acesso e validação no servidor. Esta etapa é apenas de interface e exportação local.
