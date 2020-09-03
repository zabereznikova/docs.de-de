---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132942"
---

Wenn eine Fehlermeldung wie **Unable to locate package {netcore-package}** (Das Paket {netcore-package} konnte nicht gefunden werden) oder **Some packages could not be installed** (Einige Pakete konnten nicht installiert werden) angezeigt wird, führen Sie die folgenden Befehle aus.

Die folgende Befehlsgruppe enthält zwei Platzhalter.

- `{dotnet-package}`\
Dieser steht für das .NET Core-Paket, das Sie installieren,z. B. `aspnetcore-runtime-3.1` , und wird im nachstehenden Befehl `sudo apt-get install` verwendet.

- `{os-version}`\
Dies steht für die von Ihnen genutzte Linux-Version, und wird im nachstehenden Befehl `wget` verwendet.

Versuchen Sie zunächst, die Paketliste zu löschen:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Versuchen Sie dann, .NET Core neu zu installieren. Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:
