---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524715"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Developer-Eingabeaufforderung für Visual Studio.

Die Developer-Eingabeaufforderung für Visual Studio legt die Umgebungsvariablen, die Ihnen die einfache Nutzung von .NET Framework-Tools ermöglichen, automatisch fest.

> [!div class="button"]
[Herunterladen von Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a>Suchen nach der Eingabeaufforderung auf Ihrem Computer

Abhängig von der Version von Visual Studio und jeglichen zusätzlichen installierten SDKs verfügen Sie möglicherweise über mehrere Eingabeaufforderungen. Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit. (Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie versuchen, [die Dateien manuell auf Ihrem Computer zu finden](#manually-locating-the-files-on-your-machine) oder [die Eingabeaufforderung innerhalb von Visual Studio auszuführen](#running-command-prompt-from-inside-visual-studio).

### <a name="in-windows-10"></a>In Windows 10

1. Geben Sie den Namen des Tools im Suchfeld auf der Taskleiste ein, z.B. `dev` oder `developer command prompt`. Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen. Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.

2. Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.

### <a name="in-windows-81"></a>Unter Windows 8.1

1. Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.

2. Drücken Sie auf dem Bildschirm **Start** `CTRL + TAB`, um die Liste **Apps** zu öffnen, und geben Sie anschließend `V` ein. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.

3. Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.

### <a name="in-windows-8"></a>Unter Windows 8

1. Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.

2. Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.

3. Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.

4. Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.

### <a name="in-windows-7"></a>Unter Windows 7

1. Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.

2. Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.

Wenn Sie andere SDKs installiert haben, z.B. das [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) oder [frühere Versionen](https://developer.microsoft.com/windows/downloads/sdk-archive), werden Ihnen möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen angezeigt. Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.

## <a name="manually-locate-the-files-on-your-machine"></a>Manuelles Suchen der Dateien auf Ihrem Computer

In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start Menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools“. Wenn die Suche nach der Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden. Suchen Sie z.B. den Namen der Eingabeaufforderungsdatei (z.B. *VsDevCmd.bat*), oder wechseln Sie zum Ordner „Tools“, z.B. unter „ C:\Programme (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools“ (der Pfad kann gemäß der Version, der Edition und des Speicherorts von Visual Studio von diesem Beispiel abweichen).

## <a name="run-command-prompt-from-inside-visual-studio"></a>Ausführen der Eingabeaufforderung innerhalb von Visual Studio

Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü **Extras** in Visual Studio hinzufügen. Fügen Sie das Tool der Liste externer Tools hinzu, damit Sie auf dieses zugreifen können. Folgende Schritte müssen ausgeführt werden:

1. Öffnen Sie Visual Studio.

2. Klicken Sie auf das Menü **Extras**, und wählen Sie dann **Externe Tools** aus.

3. Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus. Ein neuer Eintrag wird angezeigt.

4. Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.

5. Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.

6. Geben Sie im Feld **Argumente** an, wo diejenige Eingabeaufforderung, die Sie verwenden möchten, zu finden ist, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (dieser Befehl startet die Developer-Eingabeaufforderung, die mit Visual Studio 2017 Enterprise installiert wurde). Ändern Sie diesen Wert entsprechend der Version, der Edition und dem Installationsspeicherort von Visual Studio.

7. Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.

8. Klicken Sie auf die Schaltfläche **OK** .

   Das neue Menüelement wird hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.

## <a name="see-also"></a>Siehe auch

- [Extras](../../../docs/framework/tools/index.md)
- [Verwalten von externen Tools](/visualstudio/ide/managing-external-tools)
