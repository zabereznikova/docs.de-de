---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614447"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Sicherstellen, dass System.Uri einen konsistenten reservierten Zeichensatz verwendet

#### <a name="details"></a>Details

In <xref:System.Uri?displayProperty=fullName> sind bestimmte prozentcodierte Zeichen, die manchmal decodiert wurden, jetzt konsistent linkscodiert. Dies tritt für die Eigenschaften und Methoden auf, die auf die Pfad-, Abfrage-, Fragment- oder Benutzerinformationenkomponenten des URIs zugreifen. Das Verhalten ändert sich nur, wenn die beiden folgenden Bedingungen erfüllt sind:

- Der URI enthält die codierte Form eines der folgenden reservierten Zeichen: `:`, `'`, `(`, `)`, `!` oder `*`.
- Der URI enthält ein Unicode- oder nicht codiertes reserviertes Zeichen. Wenn beide oben genannten Kriterien erfüllt sind, werden die codierten reservierten Zeichen linkscodiert. In früheren Versionen von .NET Framework wurden sie decodiert.

#### <a name="suggestion"></a>Vorschlag

Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist dieses neue Decodierungsverhalten standardmäßig aktiviert. Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist das neue Decodierungsverhalten standardmäßig deaktiviert. Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri?displayProperty=nameWithType>
