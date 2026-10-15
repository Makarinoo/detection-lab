# Detection Lab

Règles de détection **Sigma** pour les attaques Active Directory, mappées sur
**MITRE ATT&CK** et **testées automatiquement** sur de vrais journaux d'attaque Windows.

L'idée : une règle de détection, c'est du code. Elle se versionne, se relit et se
teste. Chaque règle de ce dépôt est rejouée en CI contre des fichiers EVTX publics
qui contiennent l'attaque visée. Si la règle ne se déclenche plus, la CI échoue.

> Projet complémentaire de mon [lab SOC / Active Directory](https://github.com/Makarinoo/soc-ad-lab) :
> ici, tout tourne sans infrastructure, sur des datasets publics.

---

## Avancement

- [x] Structure du dépôt
- [ ] 10 règles Sigma sur des attaques AD, mappées ATT&CK
- [ ] CI GitHub Actions : chaque règle testée avec Chainsaw sur les EVTX publics
- [ ] Carte de couverture ATT&CK Navigator générée automatiquement

## Structure

```
rules/windows/   règles Sigma (une attaque = un fichier .yml)
tests/           correspondance règle → fichier EVTX qui doit la déclencher
docs/            couverture ATT&CK, notes sur chaque détection
```

## Sources de données

- [EVTX-ATTACK-SAMPLES](https://github.com/sbousseaden/EVTX-ATTACK-SAMPLES) — journaux Windows d'attaques réelles, classés par tactique ATT&CK

## Licence

[MIT](LICENSE)
