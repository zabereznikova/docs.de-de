---
ms.openlocfilehash: fbc39b6e1cc19f6c2846caaabb9a8a721494b4e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804073"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Zulassen von Unicode in URIs, die UNC-Freigaben ähneln

|   |   |
|---|---|
|Details|In <xref:System.Uri?displayProperty=fullName> führt das Erstellen eines Datei-URI, der sowohl einen UNC-Freigabenamen als auch Unicode-Zeichen enthält, nicht mehr zu einem URI mit ungültigem internen Status. Das Verhalten ändert sich erst, wenn alle folgenden Punkte erfüllt sind:<ul><li>Der URI hat das Schema <code>file:</code>, auf das vier oder mehr Schrägstriche folgen.</li><li>Der Hostname beginnt mit einem Unterstrich oder anderem nicht reservierten Symbol.</li><li>Der URI enthält Unicode-Zeichen.</li></ul>|
|Vorschlag|Anwendungen, die mit URIs arbeiten, die durchgängig Unicode enthalten, hätten dieses Verhalten möglicherweise nutzen können, um Verweise auf UNC-Freigaben zu unterbinden. Diese Anwendungen sollten stattdessen <xref:System.Uri.IsUnc> verwenden.|
|Bereich|Microsoft Edge|
|Version|4.7.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
