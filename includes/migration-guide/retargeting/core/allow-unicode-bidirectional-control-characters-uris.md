---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614426"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Zulassen bidirektionaler Unicode-Steuerzeichen in URIs

#### <a name="details"></a>Details

Unicode gibt mehrere spezielle Steuerzeichen an, um die Ausrichtung von Text anzugeben. In früheren Versionen von .NET Framework wurden diese Zeichen selbst dann fälschlicherweise aus allen URIs entfernt, wenn sie in ihrer prozentcodierten Form vorlagen. Damit [RFC 3987](https://tools.ietf.org/html/rfc3987) besser berücksichtigt wird, sind diese Zeichen in URIs nun zulässig. Wenn sie uncodiert in einem URI gefunden werden, werden sie prozentcodiert. Wenn sie prozentcodiert gefunden werden, bleiben sie unverändert.

#### <a name="suggestion"></a>Vorschlag

Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig aktiviert. Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig deaktiviert. Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri?displayProperty=nameWithType>
