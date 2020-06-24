---
ms.openlocfilehash: 7d398df060c031ae891218b82a2712d74f4c33b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602747"
---

Führen Sie die folgenden Befehle aus, wenn Sie eine ähnliche Fehlermeldung wie **Das Paket {netcore-package} wurde nicht gefunden** erhalten.

Die folgende Befehlsgruppe enthält zwei Platzhalter.

- `{dotnet-package}`\
Dieser steht für das .NET Core-Paket, das Sie installieren,z. B. `aspnetcore-runtime-3.1` , und wird im nachstehenden Befehl `sudo apt-get install` verwendet.

- `{os-version}`\
Dies steht für die von Ihnen genutzte Linux-Version, und wird im nachstehenden Befehl `wget` verwendet.

Löschen Sie die Paketliste:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {dotnet-package}
```

Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:
