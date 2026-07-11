# spyke-legal

Documents légaux de l'app Spyke, publiés via GitHub Pages (thème Jekyll Primer).

URLs publiées :

- https://vinceduong.github.io/spyke-legal/privacy — Politique de confidentialité (FR)
- https://vinceduong.github.io/spyke-legal/terms — Conditions d'utilisation (FR)
- https://vinceduong.github.io/spyke-legal/privacy-en — Privacy Policy (EN)
- https://vinceduong.github.io/spyke-legal/terms-en — Terms of Use (EN)

## Source de vérité

Les documents sources vivent dans le repo de l'app : `weightlifting-tracker/legal/*.md`.
Ils y sont aussi embarqués dans l'app (écran légal offline) via `scripts/build-legal.mjs`,
avec un test CI qui verrouille la synchro. **Ne pas éditer les .md ici directement.**

## Mettre à jour

Depuis le repo de l'app :

```sh
cp legal/privacy.fr.md ../spyke-legal/privacy.md
cp legal/privacy.en.md ../spyke-legal/privacy-en.md
cp legal/terms.fr.md ../spyke-legal/terms.md
cp legal/terms.en.md ../spyke-legal/terms-en.md
cd ../spyke-legal && git commit -am "docs: mise à jour des documents" && git push
```

(Et dans le repo app : `node scripts/build-legal.mjs && npx biome check --write lib/legal/legal-content.ts`.)
