---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920736"
---

Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` angezeigt. Allgemein gesagt, bedeutet dieser Fehler, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten. Während eines Upgrades sollte der Paketfeed maximal 2 Stunden lang nicht verfügbar sein. Wenn dieser Fehler länger als 2 Stunden auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.
