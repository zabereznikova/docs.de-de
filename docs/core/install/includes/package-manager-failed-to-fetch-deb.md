---
ms.openlocfilehash: 3bb59ba23214f67100d3a78bb689c941b2d187e6
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506965"
---

Beim Installieren des .NET-Pakets wird möglicherweise eine Fehlermeldung wie `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` angezeigt. Diese kann bedeuten, dass der Paketfeed für .NET mit neueren Paketversionen aktualisiert wird und Sie den Vorgang zu einem späteren Zeitpunkt wiederholen sollten. Während eines Upgrades darf der Paketfeed maximal 30 Minuten nicht verfügbar sein. Wenn dieser Fehler länger als 30 Minuten auftritt, melden Sie ein Issue auf <https://github.com/dotnet/core/issues>.
