---
ms.openlocfilehash: 8c05af045d2d9666b20f36e36c68cc853f906eae
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506857"
---

Beim Installieren des .NET-Pakets wird möglicherweise ein Fehler wie `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` angezeigt. Dieser Fehler bedeutet, dass ein Upgrade des Paketfeeds für .NET mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten. Während eines Upgrades sollte der Paketfeed maximal 2 Stunden lang nicht verfügbar sein. Wenn dieser Fehler länger als 2 Stunden auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.
