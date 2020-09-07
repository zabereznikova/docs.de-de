---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497437"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Zulassen von Unicode in URIs, die UNC-Freigaben ähneln

#### <a name="details"></a>Details

In <xref:System.Uri?displayProperty=fullName> führt das Erstellen eines Datei-URI, der sowohl einen UNC-Freigabenamen als auch Unicode-Zeichen enthält, nicht mehr zu einem URI mit ungültigem internen Status. Das Verhalten ändert sich erst, wenn alle folgenden Punkte erfüllt sind:<ul><li>Der URI hat das Schema <code>file:</code>, auf das vier oder mehr Schrägstriche folgen.</li><li>Der Hostname beginnt mit einem Unterstrich oder anderem nicht reservierten Symbol.</li><li>Der URI enthält Unicode-Zeichen.</li></ul>

#### <a name="suggestion"></a>Vorschlag

Anwendungen, die mit URIs arbeiten, die durchgängig Unicode enthalten, hätten dieses Verhalten möglicherweise nutzen können, um Verweise auf UNC-Freigaben zu unterbinden. Diese Anwendungen sollten stattdessen <xref:System.Uri.IsUnc> verwenden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
