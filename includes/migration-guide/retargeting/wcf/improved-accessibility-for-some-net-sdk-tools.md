---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614547"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Verbesserte Barrierefreiheit für einige .NET SDK-Tools

#### <a name="details"></a>Details

Im .NET Framework SDK 4.7.1 wurden die Tools „SvcConfigEditor.exe“ und „SvcTraceViewer.exe“ verbessert, indem verschiedene Probleme mit der Barrierefreiheit behoben wurden. Bei den meisten handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden. Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden. Diese Problembehebungen ändern vorherige Verhalten wie z.B. die Tastaturfokusreihenfolge. Sie können der Datei „app.config“ Folgendes hinzufügen, um alle Problembehebungen für die Barrierefreiheit in diesen Tools nutzen zu können:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |
