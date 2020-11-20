---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506958"
---

Wenn eine Fehlermeldung wie **Unable to locate package {dotnet-package}** (Das Paket {dotnet-package} konnte nicht gefunden werden) oder **Some packages could not be installed** (Einige Pakete konnten nicht installiert werden) angezeigt wird, führen Sie die folgenden Befehle aus.

Die folgende Befehlsgruppe enthält zwei Platzhalter.

- `{dotnet-package}`\
Dieser steht für das .NET-Paket, das Sie installieren, z. B. `aspnetcore-runtime-3.1`. Dies wird im folgenden Befehl `sudo apt-get install` verwendet.

- `{os-version}`\
Dies steht für die von Ihnen genutzte Linux-Version, und wird im nachstehenden Befehl `wget` verwendet.

Versuchen Sie zunächst, die Paketliste zu löschen:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Versuchen Sie dann, .NET noch mal zu installieren. Wenn dies nicht funktioniert, können Sie mithilfe der folgenden Befehle eine manuelle Installation ausführen:
