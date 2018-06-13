---
title: Developer-Eingabeaufforderung für Visual Studio.
ms.date: 03/30/2017
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
ms.openlocfilehash: d3ff897e37e3fa2f7202a54c05c8093ba05282c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402027"
---
# <a name="developer-command-prompt-for-visual-studio"></a>Developer-Eingabeaufforderung für Visual Studio.
Die Developer-Eingabeaufforderung für Visual Studio legt die Umgebungsvariablen, die Ihnen die einfache Nutzung von .NET Framework-Tools ermöglichen, automatisch fest. Die Developer-Eingabeaufforderung wird mit vollständigen oder Community-Editionen von Visual Studio installiert. Sie wird nicht mit den Express-Versionen von Visual Studio installiert.  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a>Suchen nach der Eingabeaufforderung auf Ihrem Computer  
 Je nach Version von Visual Studio und den installierten zusätzlichen SDKs werden möglicherweise mehrere Eingabeaufforderungen angezeigt. Beispielsweise stellen 64-Bit-Versionen von Visual Studio sowohl 32-Bit- als auch 64-Bit-Eingabeaufforderungen bereit. (Die 32-Bit- und 64-Bit-Versionen der meisten Tools sind identisch. Möglicherweise nehmen jedoch einige Tools bestimmte Änderungen an der 32-Bit- bzw. der 64-Bit-Umgebung vor.) Wenn die folgenden Schritte nicht funktionieren, können Sie die Aktion [Manuelles Suchen der Dateien auf Ihrem Computer](#alternative) oder [Ausführen der Eingabeaufforderung innerhalb von Visual Studio](#visualstudio) testweise ausführen.  
  
 **Unter Windows 10**  
  
1.  Öffnen Sie das Menü **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.  
  
2.  Geben Sie im Menü**Start** `dev` ein. Dadurch wird eine Liste der installierten Apps angezeigt, die Ihrem Suchmuster entsprechen. Wenn Sie nach einer anderen Eingabeaufforderung suchen, geben Sie einen anderen Suchbegriff als `prompt` ein.  
  
3.  Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.  
  
 **Unter Windows 8.1**  
  
1.  Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.  
  
2.  Drücken Sie auf dem Bildschirm **Start** `CTRL + TAB`, um die Liste **Apps** zu öffnen, und geben Sie anschließend `V` ein. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.  
  
3.  Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.  
  
 **Unter Windows 8**  
  
1.  Wechseln Sie zum Bildschirm **Start**, indem Sie beispielsweise die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") auf der Tastatur drücken.  
  
2.  Drücken Sie auf dem Bildschirm **Start** die Windows-Logo-Taste ![Windows-Logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.  
  
3.  Wählen Sie im unteren Bereich des Bildschirms das Symbol **Apps-Ansicht** aus, und geben Sie anschließend `V` ein. Dadurch wird eine Liste angezeigt, die alle installierten Visual Studio-Eingabeaufforderungen enthält.  
  
4.  Wählen Sie **Developer-Eingabeaufforderung** (oder die gewünschte Eingabeaufforderung) aus.  
  
 **Unter Windows 7**  
  
1.  Wählen Sie **Start** aus, erweitern Sie **Alle Programme**, und erweitern Sie anschließend **Microsoft Visual Studio**.  
  
2.  Wählen Sie abhängig von der installierten Visual Studio-Version **Visual Studio-Tools**, **Visual Studio-Eingabeaufforderung** oder die gewünschte Eingabeaufforderung aus.  
  
 Wenn Sie das [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) oder [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installiert haben, sehen Sie möglicherweise zusätzliche Eingabeaufforderungen für ARM-, x86- oder x64-Architekturen. Informationen dazu, welche Version der Eingabeaufforderung Sie verwenden sollten, finden Sie in der Dokumentation der einzelnen Tools.  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a>Manuelles Suchen der Dateien auf Ihrem Computer  
  In der Regel werden die Tastenkombinationen für die installierten Eingabeaufforderungen im Ordner **Start menu** für Visual Studio platziert, beispielsweise in „C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools“.    Wenn die Suche nach einer Eingabeaufforderung jedoch nicht die erwarteten Ergebnisse liefert, können Sie versuchen, die Tastenkombination manuell auf Ihrem Computer zu finden, um sie zu verwenden.   Suchen Sie z. B. den Namen der Eingabeaufforderungsdatei (z. B.„VsDevCmd.bat“), oder wechseln Sie zum Ordner „Tools“, z. B. „C:\Program Files (X 86) \Microsoft Visual Studio 14.0\Common7\Tools“ (gemäß der Version und des Installationspfads von Visual Studio kann der Pfad von diesem Beispiel abweichen).  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a>Ausführen der Eingabeaufforderung innerhalb von Visual Studio  
 Für den einfacheren Zugriff können Sie die Developer-Eingabeaufforderung von Visual Studio oder eine beliebige andere Eingabeaufforderung zum Menü „Extras“ in Visual Studio hinzufügen, indem Sie sie zur Liste der externen Tools hinzufügen. Dazu gehen Sie wie folgt vor:  
  
1.  Öffnen Sie Visual Studio.  
  
2.  Wählen Sie das Menü **Tools** und anschließend **Externe Tools...** aus.  
  
3.  Wählen Sie im Dialogfeld **Externe Tools** die Schaltfläche **Hinzufügen** aus. Ein neuer Eintrag wird angezeigt.  
  
4.  Geben Sie einen **Titel** für das neue Menüelement ein, z.B. `Command Prompt`.  
  
5.  Geben Sie im Feld **Befehl** die Datei an, die Sie starten möchten, z.B. `%comspec%` oder `C:\Windows\System32\cmd.exe`.  
  
6.  Geben Sie im Feld **Argumente** an, wo Sie die bestimmte Eingabeaufforderung finden, die Sie verwenden möchten, z.B. `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (hierdurch wird die Developer-Eingabeaufforderung mit [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)] installiert). Dieser Wert muss entsprechend der Visual Studio-Version und des Installationspfads geändert werden.  
  
7.  Wählen Sie einen Wert für das Feld **Ausgangsverzeichnis** aus, z.B. **Projektverzeichnis**.  
  
8.  Klicken Sie auf die Schaltfläche **OK** .  
  
 Anschließend wird das neue Menüelement hinzugefügt, und Sie können über das Menü **Extras** auf die Eingabeaufforderung zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Extras](../../../docs/framework/tools/index.md)  
 [Verwalten von externen Tools](/visualstudio/ide/managing-external-tools)
