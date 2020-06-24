---
ms.openlocfilehash: 15418d1ac3ade6a0fa35ca61a02134e20af1baea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602741"
---

Beim Installieren des .NET Core-Pakets wird möglicherweise ein Fehler wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt. Dieser Fehler kann bedeuten, dass ein Upgrade des Paketfeeds für .NET Core mit neueren Paketversionen durchgeführt wird und Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten. Während eines Upgrades darf der Paketfeed maximal 30 Minuten nicht verfügbar sein. Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.
