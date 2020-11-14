---
title: Installieren der lokalisierten IntelliSense-Dateien
description: Erfahren Sie, wie Sie Ihren Entwicklungscomputer für die Verwendung lokalisierter IntelliSense-Dateien für .NET 5-Projekte (einschließlich .NET-Core) und höher in Visual Studio einrichten.
ms.date: 11/06/2020
ms.openlocfilehash: 45eeae12ca79179cacb3d48fca28118de70e0a4f
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506765"
---
# <a name="how-to-install-localized-intellisense-files-for-net"></a>Installieren lokalisierter IntelliSense-Dateien für .NET

[IntelliSense](/visualstudio/ide/using-intellisense) ist ein Hilfsmittel zur Codevervollständigung, das in verschiedenen integrierten Entwicklungsumgebungen (IDEs), z. B. Visual Studio, verfügbar ist. Wenn Sie .NET-Projekte entwickeln, enthält das SDK standardmäßig nur die englische Version der IntelliSense-Dateien. In diesem Artikel erfahren Sie:

- wie Sie die lokalisierte Version dieser Dateien installieren.
- wie Sie die Visual Studio-Installation ändern, um eine andere Sprache zu verwenden.

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core) oder eine höhere Version wie [.NET 5 SDK](https://dotnet.microsoft.com/download/dotnet/5.0)
- [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder eine neuere Version.

## <a name="download-and-install-the-localized-intellisense-files"></a>Herunterladen und Installieren der lokalisierten IntelliSense-Dateien

> [!IMPORTANT]
> Für diese Prozedur ist es erforderlich, dass Sie über Administratorberechtigungen zum Kopieren der IntelliSense-Dateien in den .NET-Installationsordner verfügen.

1. Navigieren Sie zur [Seite zum Herunterladen der IntelliSense-Dateien](https://dotnet.microsoft.com/download/intellisense).

1. Laden Sie die IntelliSense-Datei für die Sprache und Version herunter, die Sie verwenden möchten.

1. Extrahieren Sie den Inhalt der ZIP-Datei.

1. Navigieren Sie zum IntelliSense-Ordner für .NET.

   1. Navigieren Sie zum .NET-Installationsordner. Standardmäßig befindet sich dieser unter *%ProgramFiles%\dotnet\packs*.
   1. Wählen Sie aus, für welches SDK Sie IntelliSense installieren möchten, und navigieren Sie zum zugehörigen Pfad. Sie haben die folgenden Optionen:

      | SDK-Typ              | `Path`                               |
      |-----------------------|------------------------------------|
      | .NET 5 oder höher und .NET Core | *Microsoft.NETCore.App.Ref*        |
      | Windows-Desktop       | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET Standard         | *NETStandard.Library.Ref*          |

   1. Navigieren Sie zur Version, für die Sie die lokalisierte IntelliSense-Datei installieren möchten. Beispielsweise *5.0.0*.
   1. Öffnen Sie den *ref* -Ordner.
   1. Öffnen Sie den Monikerordner. Zum Beispiel: *net5.0*.

   Der vollständige Pfad, zu dem Sie navigieren würden, würde also in etwa wie folgt aussehen: *C:\Programme\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.

1. Erstellen Sie einen Unterordner innerhalb des soeben geöffneten Monikerordners. Der Name des Ordners gibt an, welche Sprache Sie verwenden möchten. In der folgenden Tabelle werden die verschiedenen Optionen aufgeführt:

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

1. Kopieren Sie die *XML* -Dateien, die Sie in Schritt 3 extrahiert haben, in diesen neuen Ordner. Die *XML* -Dateien sind nach SDK-Ordnern aufgeschlüsselt. Kopieren Sie diese also in den entsprechenden SDK-Ordner, den Sie in Schritt 4 ausgewählt haben.

## <a name="modify-visual-studio-language"></a>Ändern der Sprache in Visual Studio

Damit Visual Studio eine andere Sprache für IntelliSense verwenden kann, installieren Sie das entsprechende Sprachpaket. Dies kann [während der Installation](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) oder zu einem späteren Zeitpunkt durch Ändern der Visual Studio-Installation erfolgen. Wenn Sie Visual Studio bereits auf die Sprache Ihrer Wahl konfiguriert haben, ist Ihre IntelliSense-Installation bereit.

### <a name="install-the-language-pack"></a>Installieren des Sprachpakets

Wenn Sie das gewünschte Sprachpaket während des Setups nicht installiert haben, aktualisieren Sie Visual Studio wie folgt, um das Sprachpaket zu installieren:

> [!IMPORTANT]
> Sie müssen sich mit einem Konto mit Administratorberechtigung anmelden, um Visual Studio zu installieren, zu aktualisieren oder zu ändern. Weitere Informationen finden Sie unter [Benutzerberechtigungen und Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

1. Suchen Sie den Visual Studio-Installer auf Ihrem Computer.

   Auf einem Computer mit Windows 10 wählen Sie beispielsweise **Start** und blättern dann zum Buchstaben **V** , wo das Installationsprogramm als **Visual Studio-Installer** angezeigt wird.

   ![Öffnen des Visual Studio-Installer unter Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > Sie können den Visual Studio-Installer auch an folgendem Speicherort finden:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   Möglicherweise müssen Sie den Installer aktualisieren, bevor Sie fortfahren. Wenn dies der Fall ist, befolgen Sie die Anweisungen.

1. Suchen Sie im Installer nach der Edition von Visual Studio, der Sie das Sprachpaket hinzufügen möchten, und wählen Sie dann **Ändern** aus.

   ![Aktualisieren oder Ändern von Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > Wenn die Schaltfläche **Ändern** nicht angezeigt wird, aber stattdessen eine Schaltfläche **Aktualisieren** angezeigt wird, müssen Sie Visual Studio aktualisieren, bevor Sie Ihre Installation ändern können.
   > Sobald die Aktualisierung abgeschlossen ist, sollte die Schaltfläche **Ändern** erscheinen.

1. Wählen Sie auf der Registerkarte **Sprachpakete** die Sprachen aus oder ab, die Sie installieren bzw. deinstallieren möchten.

   ![Registerkarte der Sprachpakete in Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. Klicken Sie auf **Ändern**. Das Update startet.

### <a name="modify-language-settings-in-visual-studio"></a>Ändern der Spracheinstellungen in Visual Studio

Nachdem Sie die gewünschten Sprachpakete installiert haben, ändern Sie Ihre Visual Studio-Einstellungen, um eine andere Sprache zu verwenden:

1. Öffnen Sie Visual Studio.

1. Wählen Sie im Startfenster **Ohne Code fortfahren** aus.

1. Wählen Sie in der Menüleiste **Tools** > **Optionen** aus. Das Dialogfeld „Optionen“ wird geöffnet.

1. Wählen Sie unter dem Knoten **Umgebung** **Internationale Einstellungen** aus.

1. Wählen Sie aus der **Sprachen** -Dropdownliste eine Sprache Ihrer Wahl aus. Klicken Sie auf **OK**.

1. Ein Dialogfeld informiert Sie, dass Sie Visual Studio neu starten müssen, damit die Änderungen wirksam werden. Klicken Sie auf **OK**.

1. Starten Sie Visual Studio neu.

Danach sollte IntelliSense wie erwartet funktionieren, wenn Sie ein .NET-Projekt öffnen, das auf die Version der soeben installierten IntelliSense-Dateien ausgelegt ist.

## <a name="see-also"></a>Weitere Informationen

- [IntelliSense in Visual Studio](/visualstudio/ide/using-intellisense)
