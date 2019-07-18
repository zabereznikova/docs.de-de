---
ms.openlocfilehash: d3c6818861f8b0261a9a71a4654029143d928d08
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856963"
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

