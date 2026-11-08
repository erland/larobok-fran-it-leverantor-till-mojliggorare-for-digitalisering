# Från IT-leverantör till möjliggörare för digitalisering

Officiellt bokprojekt initierat från Lärobokskaparen Engine 1.3.6. Profil: faktabok (`factbook`).

Den godkända bokplanen finns i `docs/bokplan-godkand.md` och kapitelordningen i `docs/kapitelplan.md`. Alla 13 kritiskt granskade CAP-IT-underlag och YAML-modeller finns oförändrade i `docs/kallmaterial/`; de är källor och är **inte** automatiskt med i bokexporten.

`chapters/00-inledning.md` är ett kort utkast. Huvudkapitlen ska skrivas/redigeras och granskas stegvis innan de läggs till i `book.yaml`.

**Viktigt:** författarnamn och omslag är inte beslutade. Metadatafältet `author` innehåller endast en explicit tillfällig platshållare för projektvalidering och får inte användas som slutlig författarkreditering eller i publicerad export.

## Kontroller

```bash
python scripts/project_integrity.py verify .
python scripts/validate_project.py
```

Bygg inte PDF/EPUB före beslut om författare och granskning av manus.
