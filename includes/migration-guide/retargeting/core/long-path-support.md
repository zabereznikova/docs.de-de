---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614479"
---
### <a name="long-path-support"></a>Unterstützung für lange Pfade

#### <a name="details"></a>Details

Für Apps mit der Zielplattform .NET Framework 4.6.2 und höher werden lange Pfade (bis zu 32.000 Zeichen) unterstützt, und die Beschränkung auf 260 Zeichen (oder `MAX_PATH`) für die Pfadlänge wurde aufgehoben. Bei Apps, die neu kompiliert werden, um .NET Framework 4.6.2 als Zielplattform zu verwenden, lösen Codepfade, die zuvor aufgrund der Überschreitung der Pfadlänge von 260 Zeichen <xref:System.IO.PathTooLongException?displayProperty=fullName> ausgelöst haben, nun unter den folgenden Bedingungen <xref:System.IO.PathTooLongException?displayProperty=fullName> aus:

- Die Zahl der Pfadzeichen überschreitet <xref:System.Int16.MaxValue> (32.767).
- Das Betriebssystem gibt `COR_E_PATHTOOLONG` oder einen dazu äquivalenten Wert zurück.
Bei Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit automatisch eine <xref:System.IO.PathTooLongException?displayProperty=fullName> aus, wenn ein Pfad die Länge von 260 Zeichen überschreitet.

#### <a name="suggestion"></a>Vorschlag

Für Apps mit der Zielplattform .NET Framework 4.6.2 können Sie sich gegen die Unterstützung von langen Pfaden entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer `app.config`-Datei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

Sie können bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.6.2 oder höher ausgeführt werden, lange Pfade unterstützen, indem Sie dem Abschnitt `<runtime>` der `app.config`-Datei Folgendes hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |
