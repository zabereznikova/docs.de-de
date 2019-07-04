---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424712"
---
### <a name="install-the-global-tool"></a>Installieren des globalen Tools

Paketobjekte sollten an einem geschützten Speicherort mit der Option `--tool-path` installiert werden. Diese Trennung vermeidet die gemeinsame Nutzung einer eingeschränkten Benutzerumgebung mit einer erhöhten Umgebung.

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

`/usr/local/share/dotnet-tools` wird mit der Berechtigung `drwxr-xr-x` erstellt. Wenn das Verzeichnis bereits vorhanden ist, verwenden Sie den Befehl `ls -l`, um sicherzustellen, dass der eingeschränkte Benutzer keine Berechtigung zum Bearbeiten des Verzeichnisses hat. Wenn dies der Fall ist, verwenden Sie den Befehl `sudo chmod o-w -R /usr/share/dotnet-tools`, um den Zugriff zu entfernen.

### <a name="run-the-global-tool"></a>Ausführen des globalen Tools

**Option 1** Verwenden des vollständigen Pfads mit sudo:

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

**Option 2** Hinzufügen des Symbollinks des Tools, einmal pro Tool:

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

Und ausführen mit:

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Deinstallieren des globalen Tools

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

Wenn Sie einen Symbollink erstellt haben, müssen Sie diesen ebenfalls entfernen:

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```