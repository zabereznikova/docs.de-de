---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920654"
---

Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt. Allgemein gesagt, bedeutet dieser Fehler, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird, und dass Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten. Während eines Upgrades sollte der Paketfeed maximal 30 Minuten lang nicht verfügbar sein. Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.
