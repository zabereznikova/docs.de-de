---
title: Developer-Eingabeaufforderung für Visual Studio.
description: Hier erhalten Sie Informationen zur Verwendung der Developer-Eingabeaufforderung für Visual Studio, mit der Sie .NET-Tools einfacher verwenden können. Dabei werden bestimmte Umgebungsvariablen automatisch festgelegt.
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: 92416820f47cb778dfcc916b8626df4aa328814c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167170"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Developer-Eingabeaufforderung für Visual Studio.

Mithilfe der Developer-Eingabeaufforderung für Visual Studio können Sie .NET Framework-Tools komfortabler verwenden. Es handelt sich um eine Eingabeaufforderung, die automatisch bestimmte Umgebungsvariablen festlegt. Nachdem Sie die Developer-Eingabeaufforderung geöffnet haben, können Sie die Befehle für [.NET Framework-Tools](index.md) wie `ildasm` oder `clrver` eingeben.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a>Suchen nach der Eingabeaufforderung auf Ihrem Computer

Abhängig von der Version von Visual Studio und zusätzlich installierten SDKs und Workloads verfügen Sie möglicherweise über mehrere Eingabeaufforderungen. Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locate-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio zu starten](#start-the-command-prompt-from-inside-visual-studio).

### <a name="windows-10"></a>Windows 10

1. Wählen Sie **Start** ![Windows Logo-Taste auf der Tastatur starten aus](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png), und scrollen Sie zum Buchstaben **V**.

1. Erweitern Sie den Ordner **Visual Studio 2019**.

1. Wählen Sie **Developer-Eingabeaufforderung für VS 2019** (oder die gewünschte Eingabeaufforderung) aus.

   Sie können auch beginnen, den Namen der Eingabeaufforderung in das Suchfeld auf der Taskleiste einzugeben, und das gewünschte Ergebnis auswählen, wenn die Ergebnisliste damit beginnt, um die Suchübereinstimmungen anzuzeigen.

   ![Animierte GIF-Datei, die das Suchverhalten unter Windows 10 zeigt](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a>Windows 8.1

1. Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo-Taste auf der Tastatur](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png) auf der Tastatur drücken.

1. Drücken Sie auf dem Bildschirm **Start** die Tastenkombination **STRG**+**TAB**, um die Liste **Apps** zu öffnen, und drücken Sie dann **V**. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.

1. Wählen Sie **Developer-Eingabeaufforderung für VS 2019** (oder die gewünschte Eingabeaufforderung) aus.

### <a name="windows-7"></a>Windows 7

1. Wählen Sie **Start** aus, und erweitern Sie dann **Alle Programme**.

1. Wählen Sie die **Visual Studio 2019** > **Visual Studio-Tools** > **Developer-Eingabeaufforderung für VS 2019** oder die gewünschte Eingabeaufforderung aus.

   ![Windows 7-Startmenü mit hervorgehobener Eingabeaufforderung](./media/developer-command-prompt-for-vs/windows7-menu.png)

Wenn Sie andere SDKs installiert haben, z. B. das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive), werden Ihnen möglicherweise zusätzliche Eingabeaufforderungen angezeigt. Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.

## <a name="manually-locate-the-files-on-your-machine"></a>Manuelles Suchen der Dateien auf Ihrem Computer

In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in *%:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*. Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden. Suchen Sie z. B. den Namen der Eingabeaufforderungsdatei (z. B. *VsDevCmd.bat*), oder navigieren Sie zum Ordner „Tools“, z. B. unter *%Programme (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools* (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).

## <a name="start-the-command-prompt-from-inside-visual-studio"></a>Starten der Eingabeaufforderung aus Visual Studio

Für den einfacheren Zugriff können Sie dem Menü „Extras“ in Visual Studio die Developer-Eingabeaufforderung oder eine beliebige andere Eingabeaufforderung hinzufügen. Fügen Sie das Tool der Liste externer Tools hinzu, damit Sie auf dieses zugreifen können. Folgende Schritte müssen ausgeführt werden:

1. Öffnen Sie Visual Studio.

1. Wählen Sie im Startfenster **Ohne Code fortfahren** aus.

1. Klicken Sie in der Menüleiste auf **Extras** > **Externe Tools**.

1. Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus. Ein neuer Eintrag wird angezeigt.

1. Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.

1. Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.

1. Geben Sie im Feld **Argumente** an, wo sich die bestimmte Eingabeaufforderung befindet, die Sie verwenden möchten, z. B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`. Mit diesem Befehl wird die Developer-Eingabeaufforderung gestartet, die mit Visual Studio 2019 Community installiert wird. Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.

1. Geben Sie im Feld **Ausgangsverzeichnis** das Verzeichnis an, in dem die Eingabeaufforderung gestartet wird. Wählen Sie einen Wert wie **Projektverzeichnis** aus, indem Sie den Pfeil neben dem Feld auswählen.

1. Klicken Sie auf die Schaltfläche **OK** .

   ![Dialogfeld „Externe Tools“ mit ausgefüllten Feldwerten.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   Das neue Menüelement wird hinzugefügt, und Sie können über das Menü „Extras“ auf die Eingabeaufforderung zugreifen.

   ![Menüelement „Eingabeaufforderung“ in Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a>Siehe auch

- [.NET Framework-Tools](index.md)
- [Verwalten von externen Tools](/visualstudio/ide/managing-external-tools)
- [Verwenden des Microsoft C++-Toolsets in der Befehlszeile](/cpp/build/building-on-the-command-line)
