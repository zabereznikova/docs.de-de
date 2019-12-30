---
title: Installieren lokalisierter IntelliSense-Dateien
description: Erfahren Sie, wie Sie Ihren Entwicklungscomputer einrichten, um lokalisierte IntelliSense-Dateien für .NET Core-Projekte in Visual Studio zu verwenden.
author: mairaw
ms.author: mairaw
ms.date: 12/18/2019
ms.openlocfilehash: 98d75544ab853e75c175dd2919991b250cfaa3b0
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75436673"
---
# <a name="how-to-install-localized-intellisense-files-for-net-core"></a>Installieren lokalisierter IntelliSense-Dateien für .NET Core

[IntelliSense](/visualstudio/ide/using-intellisense) ist eine Codevervollständigungshilfe, die in unterschiedlichen integrierten Entwicklungsumgebungen (IDEs) wie zum Beispiel Visual Studio verfügbar ist. In der Standardeinstellung fügt das SDK beim Entwickeln von .NET Core-Projekten die englische Version der IntelliSense-Dateien ein. In diesem Artikel wird Folgendes erläutert:

- Die Installation der lokalisierten Version dieser Dateien
- Die Änderung der Visual Studio-Installation, sodass diese eine andere Sprache verwendet

## <a name="prerequisites"></a>Erforderliche Komponenten

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine spätere Version
- [Visual Studio 2019, Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher

## <a name="download-and-install-the-localized-intellisense-files"></a>Herunterladen und Installieren der lokalisierten IntelliSense-Dateien

> [!IMPORTANT]
> Für diese Prozedur ist erforderlich, dass Sie über Administratorberechtigungen zum Kopieren der IntelliSense-Dateien in den .NET Core-Installationsordner verfügen.

1. Wechseln Sie zur Seite [Herunterladen von IntelliSense-Dateien](https://dotnet.microsoft.com/download/dotnet-core/intellisense).

1. Laden Sie die IntelliSense-Datei für die gewünschte Sprache und Version herunter.

1. Extrahieren Sie den Inhalt der ZIP-Datei.

1. Navigieren Sie zum .NET Core-Installationsordner. Dieser befindet sich in der Regel unter *%ProgramFiles%\dotnet\packs*.

   - Wählen Sie aus, für welches SDK Sie die IntelliSense-Datei installieren möchten, und navigieren Sie zum zugeordneten Pfad. Folgende Optionen stehen zur Auswahl:

      | SDK-Typ        | Pfad                               |
      | --------------- | ---------------------------------- |
      | .NET Core       | *Microsoft.NETCore.App.Ref*        |
      | Windows-Desktop | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET-Standard   | *NETStandard.Library.Ref*          |
   
   - Navigieren Sie zu der Version, für die Sie die lokalisierte IntelliSense-Datei installieren möchten, zum Beispiel *3.1.0*.
   - Öffnen Sie den Ordner *ref*.
   - Öffnen Sie den Monikerordner, zum Beispiel *netcoreapp3.1*.

   Der vollständige Pfad, zu dem Sie also navigieren würden, würde in etwa so aussehen: *C:\Programme\dotnet\packs\Microsoft.NETCore.App.Ref\3.1.0\ref\netcoreapp3.1*.

1. Erstellen Sie einen Unterordner innerhalb des Monikerordners, den Sie gerade geöffnet haben. Der Name des Ordner gibt die Sprache an, die Sie verwenden möchten. In der folgenden Tabelle sind die unterschiedlichen Optionen dargestellt:

   | Sprache              | Ordnername |
   | --------------------- | ----------- |
   | Portugiesisch (Brasilien)  | *pt-br*     |
   | Chinesisch (vereinfacht)  | *zh-hans*   |
   | Chinesisch (traditionell) | *zh-hant*   |
   | Französisch                | *fr*        |
   | Deutsch                | *de*        |
   | Italienisch               | *it*        |
   | Japanisch              | *ja*        |
   | Koreanisch                | *ko*        |
   | Russisch               | *ru*        |
   | Spanisch               | *es*        |

1. Kopieren Sie die *XML*-Datei, die Sie unter Schritt 3 in diesen neuen Ordner extrahiert haben. Die *XML*-Dateien sind durch SDK-Ordner untergliedert, kopieren Sie diese also in das entsprechende SDK, das Sie unter Schritt 4 ausgewählt haben.

## <a name="modify-visual-studio-language"></a>Ändern der Visual Studio-Sprache

Damit Visual Studio eine andere Sprache für IntelliSense verwendet, müssen Sie das entsprechende Language Pack installieren. Dies kann [während der Installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) oder zu einem späteren Zeitpunkt geschehen, indem Sie die Visual Studio-Installation ändern. Wenn Visual Studio bereits auf die Sprache Ihrer Wahl konfiguriert ist, ist Ihre IntelliSense-Installation bereit.

### <a name="install-the-language-pack"></a>So installieren Sie ein Language Pack

Wenn Sie das gewünschte Language Pack noch nicht während der Einrichtung installiert haben, aktualisieren Sie Visual Studio wie folgt, um das Language Pack zu installieren:

> [!IMPORTANT]
> Zum Installieren, Aktualisieren und Anpassen von Visual Studio müssen Sie sich mit einem Konto anmelden, das über Administratorberechtigungen verfügt. Weitere Informationen finden Sie unter [Benutzerberechtigungen und Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

1. Suchen Sie den Visual Studio-Installer auf Ihrem Computer.

   Auf einem Computer mit Windows 10 wählen Sie beispielsweise **Start** und blättern dann zum Buchstaben **V**, wo das Installationsprogramm als **Visual Studio-Installer** angezeigt wird.

   ![Öffnen des Visual Studio-Installers unter Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > Sie können den Visual Studio-Installer auch an folgendem Speicherort finden:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   Möglicherweise müssen Sie den Installer aktualisieren, bevor Sie fortfahren. Wenn dies der Fall ist, befolgen Sie die Anweisungen.

1. Suchen Sie im Installer nach der Edition von Visual Studio, der Sie das Language Pack hinzufügen möchten, und klicken Sie dann auf **Ändern**.

   ![Aktualisieren oder Ändern von Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > Wenn keine **Ändern**-Schaltfläche angezeigt wird, Sie jedoch die Schaltfläche **Aktualisieren** sehen, müssen Sie Visual Studio aktualisieren, bevor Sie Ihre Installation ändern können.
   > Nach Abschluss des Updates sollte die **Ändern**-Schaltfläche angezeigt werden.

1. Wählen Sie auf der Registerkarte **Language Pack** die Sprache oder Sprachen aus oder ab, die Sie installieren bzw. deinstallieren möchten.

   ![Registerkarte der Visual Studio-Language Packs](./media/localized-intellisense/vs-modify-language-packs.png)

1. Klicken Sie auf **Ändern**. Das Update wird gestartet.

### <a name="modify-language-settings-in-visual-studio"></a>Ändern der Spracheinstellungen in Visual Studio

Sobald Sie die gewünschten Language Packs installiert haben, ändern Sie Ihre Visual Studio-Einstellungen zur Verwendung einer anderen Sprache:

1. Öffnen Sie Visual Studio.

1. Wählen Sie im Startfenster **Ohne Code fortfahren** aus.

1. Wählen Sie im Hauptmenü die Optionen **Extras** > **Optionen** aus. Das Dialogfeld „Optionen“ wird geöffnet.

1. Wählen Sie unter dem Ordner **Umgebung** **Internationale Einstellungen** aus.

1. Wählen Sie eine Sprache aus der Dropdownliste **Sprache**. Klicken Sie auf **OK**. 

1. Ein Dialogfeld gibt an, dass Sie Visual Studio neu starten müssen, damit die Änderungen greifen. Klicken Sie auf **OK**.

1. Starten Sie Visual Studio neu.

Nach dem Neustart sollte IntelliSense erwartungsgemäß funktionieren, wenn Sie ein .NET Core-Projekt öffnen, das sich auf die Version der IntelliSense-Dateien bezieht, die Sie soeben installiert haben.

## <a name="see-also"></a>Siehe auch

- [IntelliSense in Visual Studio](/visualstudio/ide/using-intellisense)
