# CHECKLIST DE VALIDAÇÃO — Ambiente Dev

## 1. Pré-requisitos
- [x] Projeto Firebase **web-app-crm-dev** criado e ativo.
- [x] Bucket do Storage do ambiente Dev confirmado.
- [x] FlutterFlow com **Development Environment** apontando para `web-app-crm-dev`.
- [x] Opção **Manage Outside of FlutterFlow** habilitada para Storage.

## 2. Publicação de regras
- [x] Publicar `firestore.rules` no projeto Dev.
- [x] Publicar `storage.rules` no projeto Dev.
- [x] Confirmar que não houve erro no deploy.

## 3. Configuração de CORS
- [x] Aplicar `cors.json` no bucket Dev.
- [x] Validar retorno do comando `gsutil cors get`.

## 4. Configuração do FlutterFlow
- [x] Selecionar o **Development Environment**.
- [x] Conferir `APP_ENV=development`.
- [x] Conferir `FIREBASE_PROJECT_ID=web-app-crm-dev`.
- [x] Conferir `FIREBASE_STORAGE_BUCKET=gs://web-app-crm-dev.firebasestorage.app`.
- [x] Clicar em **Regenerate Config Files**.

## 5. Testes funcionais
- [x] Encerrar a sessão atual de Test Mode.
- [x] Abrir nova sessão de Test Mode.
- [x] Fazer login com usuário válido.
- [x] Confirmar leitura da imagem do usuário no app.
- [x] Confirmar upload de nova imagem em `users/{uid}/...`.
- [x] Confirmar que usuário A não consegue gravar em `users/{uidB}/...`.

## 6. Diagnóstico se ainda falhar
- [ ] Conferir no navegador se a URL da imagem abre diretamente.
- [ ] Conferir se o bucket do ambiente é realmente o bucket Dev.
- [ ] Conferir se o caminho do arquivo bate com `users/{uid}/...`.
- [ ] Conferir se o documento `/users/{uid}` existe no Firestore.
- [ ] Conferir se o campo `empresa_id` existe no documento do usuário.
- [ ] Conferir se o campo `role` existe no documento do usuário.

## 7. Ajustes futuros recomendados
- [ ] Restringir `origin` do `cors.json` em produção para os domínios oficiais.
- [ ] Refinar regras RBAC conforme papéis reais do CRM.
- [ ] Validar separação completa Dev / Prod em Firebase, FlutterFlow e GitHub.
