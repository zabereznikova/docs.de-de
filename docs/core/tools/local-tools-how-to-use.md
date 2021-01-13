---
title: 'Tutorial: Installieren und Verwenden lokaler .NET-Tools'
description: Erfahren Sie, wie Sie ein .NET-Tool als lokales Tool installieren und verwenden.
ms.topic: tutorial
ms.date: 12/11/2020
ms.openlocfilehash: f32a5c4091ff63c7c50cf339dddd89b78e543c4c
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512462"
---
# <a name="tutorial-install-and-use-a-net-local-tool-using-the-net-cli"></a>Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

In diesem Tutorial erfahren Sie, wie ein lokales Tools installiert und verwendet wird. Sie verwenden ein Tool, das Sie im [ersten Tutorial dieser Reihe](global-tools-how-to-create.md) erstellen.

## <a name="prerequisites"></a>Voraussetzungen

* Absolvieren Sie das [erste Tutorial dieser Reihe](global-tools-how-to-create.md).
* Installieren Sie die .NET Core 2.1-Runtime.

  Für dieses Tutorial installieren und verwenden Sie ein Tool, das für .NET Core 2.1 vorgesehen ist, weshalb diese Runtime auf Ihrem Computer installiert sein muss. Um die 2.1-Runtime zu installieren, besuchen Sie die [Seite zum Herunterladen von .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1). Den Link zur Installation der Runtime finden Sie in der Spalte **Run apps - Runtime**.

## <a name="create-a-manifest-file"></a>So erstellen Sie eine Manifestdatei

Um ein Tool nur für den lokalen Zugriff (für das aktuelle Verzeichnis und Unterverzeichnisse) zu installieren, muss es der Manifestdatei hinzugefügt werden.

Navigieren Sie im Ordner *microsoft.botsay* einen Schritt zurück zum Ordner *Repository*:

```console
cd ..
```

Erstellen Sie eine Manifestdatei, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen:

```dotnetcli
dotnet new tool-manifest
```

Die Ausgabe gibt an, dass die Datei erfolgreich erstellt wurde.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

Die Datei *.config/dotnet-tools.json* enthält noch keine Tools:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Die in einer Manifestdatei aufgeführten Tools stehen im aktuellen Verzeichnis und in dessen Unterverzeichnissen zur Verfügung. Das aktuelle Verzeichnis ist dasjenige, das das Verzeichnis *. config* mit der Manifestdatei enthält.

Wenn Sie einen CLI-Befehl verwenden, der ein lokales Tool referenziert, sucht das SDK im aktuellen Verzeichnis und in übergeordneten Verzeichnissen nach einer Manifestdatei. Wenn eine Manifestdatei gefunden wird, die Datei aber nicht das referenzierte Tool enthält, wird die Suche in übergeordneten Verzeichnissen fortgesetzt. Die Suche endet, wenn das referenzierte Tool oder eine Manifestdatei gefunden wird, bei der `isRoot` auf `true` festgelegt ist.

## <a name="install-botsay-as-a-local-tool"></a>Installieren von botsay als lokales Tool

Installieren Sie das Tool aus dem Paket, das Sie im ersten Tutorial erstellt haben:

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

Dieser Befehl fügt das Tool der Manifestdatei hinzu, die Sie im vorherigen Schritt erstellt haben. Die Befehlsausgabe zeigt, in welcher Manifestdatei sich das neu installierte Tool befindet:

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

Die Datei *.config/dotnet-tools.json* enthält nun ein Tool:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a>Verwenden des Tools

Rufen Sie das Tool auf, indem Sie im Ordner *repository* den Befehl `dotnet tool run` ausführen:

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>Wiederherstellen eines von anderen installierten lokalen Tools

Normalerweise installieren Sie ein lokales Tool im Stammverzeichnis des Repositorys. Nach Einchecken der Manifestdatei im Repository können andere Entwickler die neueste Manifestdatei erhalten. Um alle in der Manifestdatei aufgeführten Tools zu installieren, können sie einen einzelnen `dotnet tool restore`-Befehl ausführen.

1. Öffnen Sie die Datei *.config/dotnet-tools.json*, und ersetzen Sie den Inhalt durch den folgenden JSON-Code:

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. Ersetzen Sie `<name>` durch den Namen, den Sie bei der Erstellung des Projekts verwendet haben.

1. Speichern Sie die Änderungen.

   Diese Änderung entspricht dem Abrufen der neuesten Version aus dem Repository, nachdem eine andere Person das Paket `dotnetsay` im Projektverzeichnis installiert hat.

1. Führen Sie den Befehl `dotnet tool restore` aus.

   ```dotnetcli
   dotnet tool restore
   ```

   Der Befehl erzeugt eine Ausgabe ähnlich dem folgenden Beispiel:

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. Überprüfen Sie, ob die Tools verfügbar sind:

   ```dotnetcli
   dotnet tool list
   ```

   Die Ausgabe ist eine Liste von Paketen und Befehlen, ähnlich wie im folgenden Beispiel:

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. Testen Sie die Tools:

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a>Aktualisieren eines lokalen Tools

Die installierte Version des lokalen Tools `dotnetsay` ist 2.1.3.  Verwenden Sie den Befehl [dotnet tool update](dotnet-tool-update.md), um das Tool auf die neueste Version zu aktualisieren.

```dotnetcli
dotnet tool update dotnetsay
```

Die Ausgabe gibt die neue Versionsnummer an:

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.7'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

Der Aktualisierungsbefehl findet die erste Manifestdatei, die die Paket-ID enthält, und aktualisiert sie. Wenn es in keiner Manifestdatei im Geltungsbereich der Suche eine solche Paket-ID gibt, fügt das SDK der nächstgelegenen Manifestdatei einen neuen Eintrag hinzu. Der Suchbereich erstreckt sich über übergeordnete Verzeichnisse, bis eine Manifestdatei mit `isRoot = true` gefunden wird.

## <a name="remove-local-tools"></a>Entfernen lokaler Tools

Entfernen Sie die installierten Tools, indem Sie den Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) ausführen:

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>Problembehandlung

Falls im Verlauf des Tutorials eine Fehlermeldung angezeigt wird, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET-Tools](troubleshoot-usage-issues.md) weitere Informationen.

## <a name="see-also"></a>Siehe auch

Weitere Informationen finden Sie unter [.NET-Tools](global-tools.md).
