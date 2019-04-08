---
ms.openlocfilehash: 888628a90f615943d155c6c28762a645e36699f0
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760822"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Zulassen bidirektionaler Unicode-Steuerzeichen in URIs

|   |   |
|---|---|
|Details|Unicode gibt mehrere spezielle Steuerzeichen an, um die Ausrichtung von Text anzugeben. In früheren Versionen von .NET Framework wurden diese Zeichen selbst dann fälschlicherweise aus allen URIs entfernt, wenn sie in ihrer prozentcodierten Form vorlagen. Damit [RFC 3987](https://tools.ietf.org/html/rfc3987) besser berücksichtigt wird, sind diese Zeichen in URIs nun zulässig. Wenn sie uncodiert in einem URI gefunden werden, werden sie prozentcodiert. Wenn sie prozentcodiert gefunden werden, bleiben sie unverändert.|
|Vorschlag|Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig aktiviert. Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig deaktiviert. Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt <code>&lt;runtime&gt;</code> Ihrer Anwendungskonfigurationsdatei hinzufügen:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Bereich|Gering|
|Version|4.7.2|
|Typ|Neuzuweisung|
|Betroffene APIs|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|

