# spyke-legal

Documents légaux et page d'assistance de l'app Spyke, publiés via GitHub Pages (thème Jekyll Primer).

URLs publiées :

- https://vinceduong.github.io/spyke-legal/support — Assistance (FR, URL déclarée comme « URL de l'assistance » dans App Store Connect)
- https://vinceduong.github.io/spyke-legal/privacy — Politique de confidentialité (FR)
- https://vinceduong.github.io/spyke-legal/terms — Conditions d'utilisation (FR)
- https://vinceduong.github.io/spyke-legal/support-en — Support (EN)
- https://vinceduong.github.io/spyke-legal/privacy-en — Privacy Policy (EN)
- https://vinceduong.github.io/spyke-legal/terms-en — Terms of Use (EN)

## Source de vérité

Les documents légaux (privacy, terms) vivent dans le repo de l'app : `weightlifting-tracker/legal/*.md`.
Ils y sont aussi embarqués dans l'app (écran légal offline) via `scripts/build-legal.mjs`,
avec un test CI qui verrouille la synchro. **Ne pas éditer `privacy*.md` / `terms*.md` ici directement.**

Les pages d'assistance (`support.md`, `support-en.md`) sont web-only : elles ne sont pas embarquées
dans l'app et s'éditent directement dans ce repo.

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
