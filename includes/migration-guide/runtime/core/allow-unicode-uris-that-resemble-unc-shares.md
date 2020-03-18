---
ms.openlocfilehash: fbc39b6e1cc19f6c2846caaabb9a8a721494b4e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856963"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Zulassen von Unicode in URIs, die UNC-Freigaben ähneln

|   |   |
|---|---|
|Details|In <xref:System.Uri?displayProperty=fullName> führt das Erstellen eines Datei-URI, der sowohl einen UNC-Freigabenamen als auch Unicode-Zeichen enthält, nicht mehr zu einem URI mit ungültigem internen Status. Das Verhalten ändert sich erst, wenn alle folgenden Punkte erfüllt sind:<ul><li>Der URI hat das Schema <code>file:</code>, auf das vier oder mehr Schrägstriche folgen.</li><li>Der Hostname beginnt mit einem Unterstrich oder anderem nicht reservierten Symbol.</li><li>Der URI enthält Unicode-Zeichen.</li></ul>|
|Vorschlag|Anwendungen, die mit URIs arbeiten, die durchgängig Unicode enthalten, hätten dieses Verhalten möglicherweise nutzen können, um Verweise auf UNC-Freigaben zu unterbinden. Diese Anwendungen sollten stattdessen <xref:System.Uri.IsUnc> verwenden.|
|`Scope`|Edge|
|Version|4.7.2|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
