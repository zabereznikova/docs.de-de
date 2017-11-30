---
title: 'Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba195656363b15407aed6a4da0ab804421a3d964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt
Der zur Entwurfszeit für ein benutzerdefiniertes Steuerelement kann erweitert werden, indem Sie einen zugeordneten benutzerdefinierten Designer erstellen.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie Sie einen benutzerdefinierten Designer für ein benutzerdefiniertes Steuerelement zu erstellen. Implementieren Sie eine `MarqueeControl` Typ und einen zugeordneten Designer-Klasse mit dem Namen `MarqueeControlRootDesigner`.  
  
 Die `MarqueeControl` Typ implementiert eine Ansicht ähnlich eine Laufschrift Theater animierte Leuchten mit blinkende Text.  
  
 Der Designer für das genannte Steuerelement interagiert mit der entwurfsumgebung eine benutzerdefinierte zur Entwurfszeit zu ermöglichen. Mit dem benutzerdefinierten Designer können Sie eine benutzerdefinierte assemblieren `MarqueeControl` Implementierung mit animierten Leuchten und blinkende Text in verschiedenen Kombinationen. Sie können die assemblierte Steuerelement eines Formulars wie jedes andere Windows Forms-Steuerelement verwenden.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts  
  
-   Erstellen eines Projekts für eine Bibliothek  
  
-   Verweisen auf das benutzerdefinierte Steuerelement-Projekt  
  
-   Definieren ein benutzerdefiniertes Steuerelement und seine benutzerdefinierten Designer  
  
-   Erstellen einer Instanz eines benutzerdefinierten Steuerelements  
  
-   Einrichten des Projekts zum Debuggen zur Entwurfszeit  
  
-   Implementieren des benutzerdefinierten Steuerelements  
  
-   Erstellen ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement  
  
-   Erstellen des untergeordneten MarqueeBorder-Steuerelements  
  
-   Erstellen eines benutzerdefinierten Designers Filtereigenschaften zu Schattenkopien  
  
-   Behandlung von Änderungen an der Clientkomponenten  
  
-   Hinzufügen von Designerverben zum benutzerdefinierten Designer  
  
-   Erstellen eine benutzerdefinierte UITypeEditor  
  
-   Testen das benutzerdefinierte Steuerelement im Designer  
  
 Wenn Sie fertig sind, wird das benutzerdefinierte Steuerelement etwa wie folgt aussehen:  
  
 ![Mögliche Anordnung eines MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Das vollständige Codebeispiel finden Sie unter [Vorgehensweise: Erstellen Sie eine Windows Forms-Steuerelement, dass akzeptiert Vorteil von Entwurfszeitfunktionen](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Der erste Schritt besteht darin das Anwendungsprojekt zu erstellen. Verwenden Sie dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie eine Windows Forms-Anwendungsprojekt namens "MarqueeControlTest". Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## <a name="creating-a-control-library-project"></a>Erstellen eines Projekts für eine Bibliothek  
 Der nächste Schritt besteht darin-Steuerelementbibliothek-Projekt zu erstellen. Erstellen Sie ein neues benutzerdefiniertes Steuerelement und den entsprechenden benutzerdefinierten Designer.  
  
#### <a name="to-create-the-control-library-project"></a>-Steuerelementbibliothek-Projekt erstellen  
  
1.  Fügen Sie ein Windows Forms-Steuerelementbibliothek-Projekt zur Projektmappe hinzu. Nennen Sie das Projekt "MarqueeControlLibrary".  
  
2.  Mit **Projektmappen-Explorer**, Standardsteuerelement für das Projekt löschen, indem Sie die Quelldatei mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von einer Sprache Ihrer Wahl zu löschen. Weitere Informationen finden Sie unter [NIB: Vorgehensweise: entfernen, löschen und Ausschließen von Elementen](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element an der `MarqueeControlLibrary` Projekt. Benennen Sie die neue Quelldatei Basis von "MarqueeControl."  
  
4.  Mit **Projektmappen-Explorer**, erstellen Sie einen neuen Ordner in der `MarqueeControlLibrary` Projekt. Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen neuer Projektelemente](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce). Nennen Sie den Ordner "Entwurf".  
  
5.  Mit der rechten Maustaste die **Entwurf** Ordner, und fügen Sie eine neue Klasse hinzu. Benennen Sie der Quelldatei Basis von "MarqueeControlRootDesigner."  
  
6.  Sie müssen Typen aus der System.Design-Assembly verwenden, fügen Sie daher diese Verweis auf die `MarqueeControlLibrary` Projekt.  
  
    > [!NOTE]
    >  Um die System.Design-Assembly zu verwenden, muss das Projekt die Vollversion von .NET Framework nicht das .NET Framework-Clientprofil abzielen. Um das Zielframework ändern, finden Sie unter [wie: eine Version von .NET Framework als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).  
  
## <a name="referencing-the-custom-control-project"></a>Verweisen auf das benutzerdefinierte Steuerelement-Projekt  
 Verwenden Sie die `MarqueeControlTest` Projekt so testen Sie das benutzerdefinierte Steuerelement. Das Testprojekt wird des benutzerdefinierten Steuerelements bewusst sein, wenn Sie einen Projektverweis auf Hinzufügen der `MarqueeControlLibrary` Assembly.  
  
#### <a name="to-reference-the-custom-control-project"></a>Um auf das benutzerdefinierte Steuerelement-Projekt zu verweisen.  
  
-   In der `MarqueeControlTest` Projekt, fügen Sie einen Projektverweis auf die `MarqueeControlLibrary` Assembly. Achten Sie darauf, dass Sie verwenden die **Projekte** Registerkarte der **Verweis hinzufügen** Dialogfeld anstelle von Verweisen auf die `MarqueeControlLibrary` Assembly direkt.  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a>Definieren ein benutzerdefiniertes Steuerelement und seine benutzerdefinierten Designer  
 Das benutzerdefinierte Steuerelement ableiten der <xref:System.Windows.Forms.UserControl> Klasse. Dadurch kann das Steuerelement auf andere Steuerelemente enthalten, und gibt die Kontrolle sehr viel systemverarbeitungszeit in Standardfunktionen.  
  
 Das benutzerdefinierte Steuerelement wird einen benutzerdefinierten Designer verknüpft haben. Dies ermöglicht Ihnen die Erstellung einer eindeutigen entwurfserfahrung zugeschnitten sind speziell für das benutzerdefinierte Steuerelement.  
  
 Sie können das Steuerelement mit ihren Designer zuordnen, mithilfe der <xref:System.ComponentModel.DesignerAttribute> Klasse. Da Sie die gesamte Entwurfszeitverhalten des benutzerdefinierten Steuerelements entwickeln, implementiert der benutzerdefinierte Designer die <xref:System.ComponentModel.Design.IRootDesigner> Schnittstelle.  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Um ein benutzerdefiniertes Steuerelement und seine benutzerdefinierten Designer zu definieren.  
  
1.  Öffnen der `MarqueeControl` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Hinzufügen der <xref:System.ComponentModel.DesignerAttribute> auf die `MarqueeControl` -Klassendeklaration. Dies ordnet der Designer das benutzerdefinierte Steuerelement.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Öffnen der `MarqueeControlRootDesigner` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Ändern Sie die Deklaration von `MarqueeControlRootDesigner` zu Vererben der <xref:System.Windows.Forms.Design.DocumentDesigner> Klasse. Anwenden der <xref:System.ComponentModel.ToolboxItemFilterAttribute> an die Designer-Interaktion mit der **Toolbox**.  
  
     **Hinweis** die Definition für die `MarqueeControlRootDesigner` Klasse hat eingeschlossen wurde, in einem Namespace mit dem Namen "MarqueeControlLibrary.Design." Diese Deklaration setzt der Designer in einer speziellen Namespace für Design-bezogenen Typen reserviert.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Definieren Sie den Konstruktor für die `MarqueeControlRootDesigner` Klasse. Fügen Sie eine <xref:System.Diagnostics.Trace.WriteLine%2A> Anweisung im Konstruktortext. Dies wird für Debugzwecke hilfreich sein.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a>Erstellen einer Instanz eines benutzerdefinierten Steuerelements  
 Um die benutzerdefinierte Verhalten des Steuerelements zur Entwurfszeit zu beobachten, platzieren Sie eine Instanz des Steuerelements im Formular in `MarqueeControlTest` Projekt.  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a>Zum Erstellen einer Instanz eines benutzerdefinierten Steuerelements  
  
1.  Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element an der `MarqueeControlTest` Projekt. Benennen Sie die neue Quelldatei Basis von "DemoMarqueeControl."  
  
2.  Öffnen der `DemoMarqueeControl` in der Datei die **Code-Editor**. Importieren Sie am Anfang der Datei, die `MarqueeControlLibrary` Namespace:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Ändern Sie die Deklaration von `DemoMarqueeControl` zu Vererben der `MarqueeControl` Klasse.  
  
2.  Erstellen Sie das Projekt.  
  
3.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
4.  Suchen der **MarqueeControlTest-Komponenten** Registerkarte der **Toolbox** und öffnen Sie sie. Ziehen Sie eine `DemoMarqueeControl` aus der **Toolbox** auf das Formular.  
  
5.  Erstellen Sie das Projekt.  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts zum Debuggen zur Entwurfszeit  
 Wenn Sie eine benutzerdefinierte während der Entwurfszeit-Benutzeroberfläche entwickeln, wird Ihre Steuerelemente und-Komponenten zu debuggen sein. Es ist eine einfache Möglichkeit zum Einrichten Ihres Projekts festlegen, das Debuggen zur Entwurfszeit. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelemente zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>So richten Sie das Projekt zum Debuggen zur Entwurfszeit ein  
  
1.  Mit der rechten Maustaste die `MarqueeControlLibrary` Projekt, und wählen Sie **Eigenschaften**.  
  
2.  Wählen Sie im Dialogfeld "MarqueeControlLibrary-Eigenschaftenseiten" die **Debuggen** Seite.  
  
3.  In der **Startaktion** Abschnitt **externes Startprogramm**. Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche, um für die Visual Studio-IDE zu navigieren. Der Name der ausführbaren Datei lautet devenv.exe aus, und wenn Sie am Standardspeicherort installiert haben, lautet %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.  
  
4.  Klicken Sie auf OK, um das Dialogfeld zu schließen.  
  
5.  Mit der rechten Maustaste die `MarqueeControlLibrary` Projekt, und wählen Sie "Als Startprojekt festlegen" aus, um diese Konfiguration für Remotedebugging zu aktivieren.  
  
## <a name="checkpoint"></a>Checkpoint  
 Sie können nun das Entwurfszeitverhalten eines benutzerdefinierten Steuerelements zu debuggen. Nachdem Sie festgestellt haben, dass die debugging-Umgebung ordnungsgemäß eingerichtet ist, testen Sie die Zuordnung zwischen das benutzerdefinierte Steuerelement und dem benutzerdefinierten Designer.  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>So testen Sie das debugging-Umgebung und die Designer-Zuordnung  
  
1.  Öffnen der `MarqueeControlRootDesigner` -Quelldatei in die **Code-Editor** und fügen Sie einen Haltepunkt auf der <xref:System.Diagnostics.Trace.WriteLine%2A> Anweisung.  
  
2.  Drücken Sie F5, um die Debugsitzung zu starten. Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.  
  
3.  Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "MarqueeControlTest". Sie können auswählen, um die Projektmappe leicht zu finden **zuletzt geöffnete Projekte** aus der **Datei** Menü. Die Projektmappendatei "MarqueeControlTest.sln" werden die zuletzt verwendeten Datei aufgeführt.  
  
4.  Öffnen der `DemoMarqueeControl` im Designer. Beachten Sie, dass das Debuggen Instanz von Visual Studio den Fokus erhält, und die Ausführung am Haltepunkt hält. Drücken Sie F5, um die Debugsitzung fortzusetzen.  
  
 An diesem Punkt ist alles für Sie zum Entwickeln und Debuggen das benutzerdefinierte Steuerelement und seine zugeordneten Designer. Im weiteren Verlauf dieser exemplarischen Vorgehensweise werden auf die Informationen zum Implementieren der Funktionen des Steuerelements und der Designer konzentrieren.  
  
## <a name="implementing-your-custom-control"></a>Implementieren des benutzerdefinierten Steuerelements  
 Die `MarqueeControl` ist eine <xref:System.Windows.Forms.UserControl> mit ein wenig Anpassung. Macht zwei Methoden: `Start`, die die Animation startet und `Stop`, die die Animation beendet. Da die `MarqueeControl` enthält untergeordnete Steuerelemente, implementieren die `IMarqueeWidget` -Schnittstelle, `Start` und `Stop` aufzählen jedes untergeordnete Steuerelement, und rufen die `StartMarquee` und `StopMarquee` Methoden, bzw. für jedes untergeordnete Steuerelement implementiert `IMarqueeWidget`.  
  
 Die Darstellung von der `MarqueeBorder` und `MarqueeText` Steuerelemente ist abhängig von das Layout damit `MarqueeControl` überschreibt die <xref:System.Windows.Forms.Control.OnLayout%2A> -Methode und ruft <xref:System.Windows.Forms.Control.PerformLayout%2A> auf untergeordnete Steuerelemente dieses Typs.  
  
 Dies ist das Ausmaß von der `MarqueeControl` Anpassungen. Die Funktionen zur Laufzeit werden implementiert, indem der `MarqueeBorder` und `MarqueeText` werden Steuerelemente und die Funktionen zur Entwurfszeit implementiert die `MarqueeBorderDesigner` und `MarqueeControlRootDesigner` Klassen.  
  
#### <a name="to-implement-your-custom-control"></a>Um ein benutzerdefinierte Steuerelement implementieren  
  
1.  Öffnen der `MarqueeControl` -Quelldatei in die **Code-Editor**. Implementieren der `Start` und `Stop` Methoden.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A>-Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a>Erstellen ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement  
 Die `MarqueeControl` zwei Arten von untergeordneten Steuerelement gehostet wird: der `MarqueeBorder` Steuerelement und dem `MarqueeText` Steuerelement.  
  
-   `MarqueeBorder`: Dieses Steuerelement zeichnet einen Rahmen mit einer "Museen" seinen Rändern. Leuchten flash nacheinander, damit sie angezeigt werden, um den Rahmen verschoben werden. Die Geschwindigkeit, auf das Blinken wird gesteuert, indem Sie eine Eigenschaft mit dem Namen `UpdatePeriod`. Mehrere andere benutzerdefinierten Eigenschaften ermitteln, andere Aspekte der Darstellung des Steuerelements. Zwei Methoden, nämlich `StartMarquee` und `StopMarquee`, steuern, wenn die Animation wird gestartet und angehalten wird.  
  
-   `MarqueeText`: Dieses Steuerelement zeichnet eine blinkende Zeichenfolge. Wie die `MarqueeBorder` -Steuerelement, die Geschwindigkeit, mit der der Text blinkt, wird gesteuert durch die `UpdatePeriod` Eigenschaft. Die `MarqueeText` -Steuerelement verfügt über die `StartMarquee` und `StopMarquee` Methoden gemeinsame mit der `MarqueeBorder` Steuerelement.  
  
 Zur Entwurfszeit die `MarqueeControlRootDesigner` ermöglicht diese zwei Steuerelementtypen hinzugefügt werden, eine `MarqueeControl` in beliebiger Kombination.  
  
 Allgemeine Funktionen der beiden Steuerelemente sind in der eine Schnittstelle mit dem Namen berücksichtigt `IMarqueeWidget`. Dies ermöglicht die `MarqueeControl` Laufschrift bezogene untergeordnete Steuerelemente zu ermitteln, und Ihnen besondere Behandlung.  
  
 Um das periodische Animationsfeature zu implementieren, verwenden Sie <xref:System.ComponentModel.BackgroundWorker> Objekte aus der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace. Sie können <xref:System.Windows.Forms.Timer> Objekte, aber wenn viele `IMarqueeWidget` Objekte vorhanden sind, die einzelnen UI-Thread möglicherweise nicht mit der Animation zu halten.  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a>So erstellen ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement  
  
1.  Hinzufügen eines neuen Elements der Klasse, die `MarqueeControlLibrary` Projekt. Benennen Sie die neue Quelldatei Basis von "IMarqueeWidget."  
  
2.  Öffnen der `IMarqueeWidget` -Quelldatei in die **Code-Editor** und ändern Sie die Deklaration von `class` auf `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Fügen Sie folgenden Code, der `IMarqueeWidget` Schnittstelle, um zwei Methoden und eine Eigenschaft, die die Animation bearbeiten verfügbar zu machen:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Fügen Sie einen neuen **benutzerdefiniertes Steuerelement** Element an der `MarqueeControlLibrary` Projekt. Benennen Sie die neue Quelldatei Basis von "MarqueeText."  
  
5.  Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> -Komponente aus der **Toolbox** auf Ihre `MarqueeText` Steuerelement. Diese Komponente ermöglicht das `MarqueeText` Steuerelement selbst asynchron aktualisiert.  
  
6.  Legen Sie im Fenster Eigenschaften die <xref:System.ComponentModel.BackgroundWorker> Komponente `WorkerReportsProgess` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaften `true`. Diese Einstellungen ermöglichen die <xref:System.ComponentModel.BackgroundWorker> Komponente ausgelöst werden soll in regelmäßigen Abständen die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis sowie zum Abbrechen asynchroner Updates. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Öffnen der `MarqueeText` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Ändern Sie die Deklaration von `MarqueeText` vererbungsquelle <xref:System.Windows.Forms.Label> und zum Implementieren der `IMarqueeWidget` Schnittstelle:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Deklarieren Sie die Instanzvariablen, die verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie sie im Konstruktor. Die `isLit` Feld bestimmt, ob der Text in der Farbe, die vom gezeichnet werden die `LightColor` Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.  
  
     Die `StartMarquee` und `StopMarquee` Methoden aufrufen, die <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden zum Starten und Beenden der Animation.  
  
     Die <xref:System.ComponentModel.CategoryAttribute.Category%2A> und <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribute gelten für die `UpdatePeriod` Eigenschaft, sodass er in einem benutzerdefinierten Abschnitt des Fensters Eigenschaften namens "Laufschrift." angezeigt wird.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Implementieren Sie die Eigenschaftenaccessoren. Sie werden zwei Eigenschaften für Clients verfügbar zu machen: `LightColor` und `DarkColor`. Die <xref:System.ComponentModel.CategoryAttribute.Category%2A> und <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribute werden auf diese Eigenschaften angewendet, sodass die Eigenschaften in einem benutzerdefinierten Abschnitt des Fensters Eigenschaften namens "Laufschrift." angezeigt werden.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.  
  
     Die <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler ruht, für die Anzahl der Millisekunden, die vom angegebenen `UpdatePeriod` löst dann den <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis, bis der Code durch Aufrufen die Animation beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> -Ereignishandler wird den Text zwischen Zuständen helle und dunkle so erteilen Sie die Darstellung der blinken umgeschaltet.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode zum Aktivieren der Animation.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Drücken Sie F6, um die Projektmappe zu erstellen.  
  
## <a name="create-the-marqueeborder-child-control"></a>Erstellen des untergeordneten MarqueeBorder-Steuerelements  
 Die `MarqueeBorder` -Steuerelement ist etwas komplexer als die `MarqueeText` Steuerelement. Er verfügt über mehr Eigenschaften und die Animation in der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist komplizierter. Im Prinzip ist sehr ähnlich, um die `MarqueeText` Steuerelement.  
  
 Da die `MarqueeBorder` Steuerelement kann über untergeordnete Steuerelemente verfügen, es muss bekannt sein <xref:System.Windows.Forms.Control.Layout> Ereignisse.  
  
#### <a name="to-create-the-marqueeborder-control"></a>Beim Erstellen des Steuerelements MarqueeBorder  
  
1.  Fügen Sie einen neuen **benutzerdefiniertes Steuerelement** Element an der `MarqueeControlLibrary` Projekt. Benennen Sie die neue Quelldatei Basis von "MarqueeBorder."  
  
2.  Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> -Komponente aus der **Toolbox** auf Ihre `MarqueeBorder` Steuerelement. Diese Komponente ermöglicht das `MarqueeBorder` Steuerelement selbst asynchron aktualisiert.  
  
3.  Legen Sie im Fenster Eigenschaften die <xref:System.ComponentModel.BackgroundWorker> Komponente `WorkerReportsProgess` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaften `true`. Diese Einstellungen ermöglichen die <xref:System.ComponentModel.BackgroundWorker> Komponente ausgelöst werden soll in regelmäßigen Abständen die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis sowie zum Abbrechen asynchroner Updates. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  Klicken Sie im Fenster Eigenschaften auf die Schaltfläche "Ereignisse". Fügen Sie Handler für das <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.  
  
5.  Öffnen der `MarqueeBorder` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Ändern Sie die Deklaration von `MarqueeBorder` vererbungsquelle <xref:System.Windows.Forms.Panel> und zum Implementieren der `IMarqueeWidget` Schnittstelle.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Deklarieren Sie zwei Enumerationen für die Verwaltung der `MarqueeBorder` Zustand des Steuerelements: `MarqueeSpinDirection`, die bestimmt, die der Richtung, in denen Leuchten "" um den Rahmen und `MarqueeLightShape`, bestimmt die Form des Leuchten (oder quadratisch bzw. zirkuläre). Platzieren Sie diese Deklarationen vor der `MarqueeBorder` -Klassendeklaration.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Deklarieren Sie die Instanzvariablen, die verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie sie im Konstruktor.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.  
  
     Die `StartMarquee` und `StopMarquee` Methoden aufrufen, die <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden zum Starten und Beenden der Animation.  
  
     Da die `MarqueeBorder` -Steuerelement untergeordneten Steuerelementen enthalten kann die `StartMarquee` Methode listet alle untergeordneten Steuerelemente und Aufrufe `StartMarquee` auf die implementieren `IMarqueeWidget`. Die `StopMarquee` Methode verfügt über eine ähnliche Implementierung.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Implementieren Sie die Eigenschaftenaccessoren. Die `MarqueeBorder` Steuerelement verfügt über mehrere Eigenschaften zum Steuern der Darstellung.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.  
  
     Die <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler ruht, für die Anzahl der Millisekunden, die vom angegebenen `UpdatePeriod` löst dann den <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis, bis der Code durch Aufrufen die Animation beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.  
  
     Die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignishandler erhöht die Position des "Basis" Licht, von dem der Light/Dark-Status der anderen Leuchten bestimmt wird, und ruft die <xref:System.Windows.Forms.Control.Refresh%2A> aufzurufende Methode dazu führen, dass das Steuerelement sich selbst neu zeichnet.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Implementieren Sie die Hilfemethoden `IsLit` und `DrawLight`.  
  
     Die `IsLit` Methode bestimmt die Farbe des eine helle an einer angegebenen Position. Leuchten, die "Leuchten" in der vorgegebenen durch Farbe gezeichnet werden die `LightColor` -Eigenschaft, und solche, die "dunklen" werden in der Farbe, die vom gezeichnet werden die `DarkColor` Eigenschaft.  
  
     Die `DrawLight` -Methode zeichnet ein Licht, verwenden die entsprechende Farbe, Form und Position.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A> und <xref:System.Windows.Forms.Control.OnPaint%2A> Methoden.  
  
     Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode zeichnet die LEDs an den Rändern der `MarqueeBorder` Steuerelement.  
  
     Da die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode hängt von den Dimensionen von der `MarqueeBorder` -Steuerelement, müssen Sie sie aufrufen, sobald das Layout geändert. Um dies zu erreichen, außer Kraft setzen <xref:System.Windows.Forms.Control.OnLayout%2A> , und rufen Sie <xref:System.Windows.Forms.Control.Refresh%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Erstellen eines benutzerdefinierten Designers Filtereigenschaften zu Schattenkopien  
 Die `MarqueeControlRootDesigner` -Klasse stellt die Implementierung für den Stamm-Designer bereit. Zusätzlich zu diesem Designer, die auf wirkt der `MarqueeControl`, benötigen Sie einen benutzerdefinierten Designer, der speziell zugeordnet ist die `MarqueeBorder` Steuerelement. Dieser Designer stellt benutzerdefiniertes Verhalten, das im Rahmen des benutzerdefinierten Stammdesigners geeignet ist.  
  
 Insbesondere die `MarqueeBorderDesigner` "Schatten" und Filtern von einigen Eigenschaften wird die `MarqueeBorder` -Steuerelement, ihre Interaktion mit der entwurfsumgebung ändern.  
  
 Abfangen von Aufrufen an eine Komponente-Eigenschaftenaccessor wird als "shadowing." bezeichnet. Ermöglicht einem Designer zum Nachverfolgen des Wert, der vom Benutzer festgelegt, und übergeben Sie den Wert optional der Komponente, die entworfen wird.  
  
 In diesem Beispiel die <xref:System.Windows.Forms.Control.Visible%2A> und <xref:System.Windows.Forms.Control.Enabled%2A> Eigenschaften werden gespiegelt werden, durch die `MarqueeBorderDesigner`, die verhindert, dass des Benutzers festlegen, dass die `MarqueeBorder` Steuerelement ausgeblendet oder deaktiviert, während der Entwurfszeit.  
  
 Entwickler können auch hinzufügen und Entfernen von Eigenschaften. In diesem Beispiel die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft wird zur Entwurfszeit entfernt werden, da die `MarqueeBorder` Steuerelement programmgesteuert festgelegt, die Auffüllung, basierend auf der Größe von Leuchten, die gemäß der `LightSize` Eigenschaft.  
  
 Die Basisklasse für `MarqueeBorderDesigner` ist <xref:System.ComponentModel.Design.ComponentDesigner>, dem verfügt über Methoden, die die Attribute, Eigenschaften und Ereignisse verfügbar gemacht werden von einem Steuerelement zur Entwurfszeit ändern können:  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 Wenn Sie die öffentliche Schnittstelle einer Komponente, die mit diesen Methoden ändern, müssen Sie diesen Regeln entsprechen:  
  
-   Hinzufügen oder Entfernen von Elementen in der `PreFilter` nur Methoden  
  
-   Ändern von vorhandenen Elementen in der `PostFilter` nur Methoden  
  
-   Rufen Sie die basisimplementierung immer zuerst die `PreFilter` Methoden  
  
-   Rufen Sie die basisimplementierung immer zuletzt der `PostFilter` Methoden  
  
 Die folgenden Regeln einhalten wird sichergestellt, dass alle Designer in der Umgebung zur Entwurfszeit eine konsistente Sicht aller Komponenten entworfen wird.  
  
 Die <xref:System.ComponentModel.Design.ComponentDesigner> Klasse stellt ein Wörterbuch bereit, für die Verwaltung der Werte von Shadowing von Eigenschaften, sodass Sie keine bestimmten Nachrichteninstanzvariablen erstellen zu müssen.  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>So erstellen einen benutzerdefinierten Designer Schatten "und" Filtern von Eigenschaften  
  
1.  Mit der rechten Maustaste die **Entwurf** Ordner, und fügen Sie eine neue Klasse hinzu. Benennen Sie der Quelldatei Basis von "MarqueeBorderDesigner."  
  
2.  Öffnen der `MarqueeBorderDesigner` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Ändern Sie die Deklaration von `MarqueeBorderDesigner` vererbungsquelle <xref:System.Windows.Forms.Design.ParentControlDesigner>.  
  
     Da die `MarqueeBorder` -Steuerelement untergeordneten Steuerelementen enthalten kann `MarqueeBorderDesigner` erbt von <xref:System.Windows.Forms.Design.ParentControlDesigner>, behandelt die über-und untergeordneten Aktivität.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Überschreiben Sie die grundlegende Implementierung der <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Implementieren Sie die <xref:System.Windows.Forms.Control.Enabled%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft. Diese Implementierungen Shadowing für die Eigenschaften des Steuerelements.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a>Behandlung von Änderungen an der Clientkomponenten  
 Die `MarqueeControlRootDesigner` Klasse enthält die benutzerdefinierten zur Entwurfszeit für Ihre `MarqueeControl` Instanzen. Die meisten Funktionen zur Entwurfszeit geerbt, von der <xref:System.Windows.Forms.Design.DocumentDesigner> Klasse; Ihr Code werden zwei bestimmte Anpassungen implementieren: Behandlung von Änderungen an der Serverkomponenten und das Hinzufügen von Designerverben.  
  
 Als Benutzern beim Entwerfen ihrer `MarqueeControl` Instanzen, Nachverfolgen der Stamm-Designers Änderungen an der `MarqueeControl` und seine untergeordneten Steuerelemente. Die entwurfszeitumgebung bietet einen geeigneten Dienst <xref:System.ComponentModel.Design.IComponentChangeService>, für die Überwachung zu "Komponentenstatus" wechselt.  
  
 Sie erhalten einen Verweis auf diesen Dienst, durch Abfragen der Umgebung mit der <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> Methode. Wenn die Abfrage erfolgreich ist, kann der Designer einen Handler für Anfügen der <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> Ereignis und führen Sie die Aufgaben zum Verwalten von eines konsistenten Zustands zur Entwurfszeit erforderlich sind.  
  
 Im Fall von der `MarqueeControlRootDesigner` -Klasse, rufen Sie die <xref:System.Windows.Forms.Control.Refresh%2A> -Methode für jedes `IMarqueeWidget` Objekt in der `MarqueeControl`. Dies bewirkt, dass die `IMarqueeWidget` Objekt selbst entsprechend neu zeichnet, wenn Eigenschaften des übergeordneten Elements wie <xref:System.Windows.Forms.Control.Size%2A> geändert werden.  
  
#### <a name="to-handle-component-changes"></a>So behandeln Sie komponentenänderungen  
  
1.  Öffnen der `MarqueeControlRootDesigner` -Quelldatei in die **Code-Editor** und überschreiben die <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode. Rufen Sie die grundlegende Implementierung der <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> und Abfragen für die <xref:System.ComponentModel.Design.IComponentChangeService>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Implementieren der <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> -Ereignishandler. Die sendende Komponente-Testtyp, und es ist ein `IMarqueeWidget`, rufen Sie seine <xref:System.Windows.Forms.Control.Refresh%2A> Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a>Hinzufügen von Designerverben zum benutzerdefinierten Designer  
 Ein Designerverb ist ein mit einem Ereignishandler verknüpfter Menübefehl. Designerverben werden Kontextmenü einer Komponente zur Entwurfszeit hinzugefügt. Weitere Informationen finden Sie unter <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 Fügen Sie zwei Designerverben auf den Designern: **Test ausführen** und **Test beenden**. Diese Verben ermöglichen es Ihnen so zeigen Sie das Laufzeitverhalten des an die `MarqueeControl` zur Entwurfszeit. Diese Verben werden hinzugefügt werden, um die `MarqueeControlRootDesigner`.  
  
 Wenn **Test ausführen** wird aufgerufen, wird der Verbereignishandler Aufrufen der `StartMarquee` Methode auf die `MarqueeControl`. Wenn **Test beenden** wird aufgerufen, wird der Verbereignishandler Aufrufen der `StopMarquee` Methode auf die `MarqueeControl`. Die Implementierung der `StartMarquee` und `StopMarquee` Methoden enthaltenen Steuerelemente, implementieren diese Methoden aufrufen `IMarqueeWidget`, sodass jedes enthaltene `IMarqueeWidget` Steuerelemente im Test auch einbezogen werden.  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a>Ihre benutzerdefinierte Designer Designerverben hinzu  
  
1.  In der `MarqueeControlRootDesigner` -Klasse verwenden, fügen Sie Ereignishandler mit dem Namen `OnVerbRunTest` und `OnVerbStopTest`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Verbinden Sie diese Ereignishandler mit den entsprechenden Designerverben an. `MarqueeControlRootDesigner`erbt einen <xref:System.ComponentModel.Design.DesignerVerbCollection> von ihrer Basisklasse. Erstellen Sie zwei neue <xref:System.ComponentModel.Design.DesignerVerb> -Objekte und fügen sie dieser Auflistung in die <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a>Erstellen eine benutzerdefinierte UITypeEditor  
 Wenn Sie eine benutzerdefinierte während der Entwurfszeit-Erfahrung für Benutzer erstellen, ist es oft wünschenswert sein, eine benutzerdefinierte Aktivität mit dem Eigenschaften-Fenster erstellen. Sie können dies bewerkstelligen, indem Sie erstellen eine <xref:System.Drawing.Design.UITypeEditor>. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines UI-Typ-Editors](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).  
  
 Die `MarqueeBorder` Steuerelement macht mehrere Eigenschaften im Eigenschaftenfenster verfügbar. Zwei dieser Eigenschaften `MarqueeSpinDirection` und `MarqueeLightShape` werden durch Enumerationen dargestellt. Veranschaulicht die Verwendung des Editors für ein UI-Typ der `MarqueeLightShape` Eigenschaft hat eine zugeordnete <xref:System.Drawing.Design.UITypeEditor> Klasse.  
  
#### <a name="to-create-a-custom-ui-type-editor"></a>So erstellen einen benutzerdefinierten UI-Typ-editor  
  
1.  Öffnen der `MarqueeBorder` -Quelldatei in die **Code-Editor**.  
  
2.  In der Definition der `MarqueeBorder` Klasse deklarieren eine Klasse mit dem Namen `LightShapeEditor` abgeleitet, die <xref:System.Drawing.Design.UITypeEditor>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable aufgerufen `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>-Methode. Diese Implementierung gibt <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, weist der entwurfsumgebung Vorgehensweise beim Anzeigen der `LightShapeEditor`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>-Methode. Diese Implementierung fragt die entwurfsumgebung für ein <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Objekt. Wenn erfolgreich ist, er erstellt eine `LightShapeSelectionControl`. Die <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> Methode wird aufgerufen, um das Starten der `LightShapeEditor`. Der Rückgabewert von diesem Aufruf wird an die entwurfsumgebung zurückgegeben.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Erstellen ein Ansichtssteuerelement für Ihre benutzerdefinierte UITypeEditor  
  
1.  Die `MarqueeLightShape` Eigenschaft unterstützt zwei Arten von hell Formen: `Square` und `Circle`. Erstellen Sie ein benutzerdefiniertes Steuerelement, das ausschließlich zum Zweck der Anzeige dieser Werte im Fenster Eigenschaften verwendet. Dieses benutzerdefinierte Steuerelement wird vom verwendet Ihre <xref:System.Drawing.Design.UITypeEditor> für die Interaktion mit dem Eigenschaftenfenster.  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>So erstellen ein Ansichtssteuerelement für die benutzerdefinierte Benutzeroberfläche Typ-editor  
  
1.  Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element an der `MarqueeControlLibrary` Projekt. Benennen Sie die neue Quelldatei Basis von "LightShapeSelectionControl."  
  
2.  Ziehen Sie zwei <xref:System.Windows.Forms.Panel> -Steuerelemente aus der **Toolbox** auf die `LightShapeSelectionControl`. Nennen Sie diese `squarePanel` und `circlePanel`. Ordnen Sie sie nebeneinander angezeigt werden. Legen Sie die <xref:System.Windows.Forms.Control.Size%2A> -Eigenschaft beider <xref:System.Windows.Forms.Panel> -Steuerelementen an (60, 60). Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft von der `squarePanel` die Steuerung an (8, 10). Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft von der `circlePanel` die Steuerung an (80, 10). Legen Sie schließlich die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft von der `LightShapeSelectionControl` auf (150, 80).  
  
3.  Öffnen der `LightShapeSelectionControl` -Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei, die <xref:System.Windows.Forms.Design?displayProperty=nameWithType> Namespace:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Implementieren <xref:System.Windows.Forms.Control.Click> -Ereignishandler für das `squarePanel` und `circlePanel` Steuerelemente. Diese Methoden aufrufen, <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> beenden Sie die benutzerdefinierte <xref:System.Drawing.Design.UITypeEditor> bearbeitungssitzung.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable aufgerufen `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Deklarieren Sie eine `MarqueeLightShape` Instanzvariable aufgerufen `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  In der `LightShapeSelectionControl` -Konstruktor Anfügen der <xref:System.Windows.Forms.Control.Click> Ereignishandler an das `squarePanel` und `circlePanel` Steuerelemente <xref:System.Windows.Forms.Control.Click> Ereignisse. Außerdem definieren Sie eine Konstruktorüberladung, die weist die `MarqueeLightShape` Wert über die entwurfsumgebung für die `lightShapeValue` Feld.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  In der <xref:System.ComponentModel.Component.Dispose%2A> -Methode, trennen Sie die <xref:System.Windows.Forms.Control.Click> -Ereignishandler.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**. Öffnen Sie die Datei LightShapeSelectionControl.Designer.cs oder LightShapeSelectionControl.Designer.vb-Datei, und entfernen Sie die Standarddefinition der der <xref:System.ComponentModel.Component.Dispose%2A> Methode.  
  
5.  Implementiert die `LightShape`-Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode. Diese Implementierung wird ein ausgefülltes Quadrat und Kreis gezeichnet. Es wird den ausgewählten Wert auch markieren, indem zeichnen einen Rahmen um eine Form vom Typ bzw. der anderen.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a>Testen das benutzerdefinierte Steuerelement im Designer  
 An diesem Punkt können Sie erstellen die `MarqueeControlLibrary` Projekt. Testen Sie die Implementierung durch Erstellen eines Steuerelements, die von erben die `MarqueeControl` -Klasse, und verwenden ihn in einem Formular.  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a>So erstellen eine benutzerdefinierte MarqueeControl-Implementierung  
  
1.  Öffnen Sie `DemoMarqueeControl` im Windows Forms-Designer. Dies erstellt eine Instanz der `DemoMarqueeControl` geben und zeigt ihn in einer Instanz von der `MarqueeControlRootDesigner` Typ.  
  
2.  In der **Toolbox**öffnen die **MarqueeControlLibrary Komponenten** Registerkarte. Daraufhin werden die `MarqueeBorder` und `MarqueeText` Steuerelemente zur Auswahl zur Verfügung.  
  
3.  Ziehen Sie eine Instanz von der `MarqueeBorder` -Steuerelement auf die `DemoMarqueeControl` Entwurfsoberfläche angezeigt. Docken Sie dieses `MarqueeBorder` Steuerelement an das übergeordnete Steuerelement.  
  
4.  Ziehen Sie eine Instanz von der `MarqueeText` -Steuerelement auf die `DemoMarqueeControl` Entwurfsoberfläche angezeigt.  
  
5.  Erstellen Sie die Projektmappe.  
  
6.  Mit der rechten Maustaste die `DemoMarqueeControl` und wählen Sie im Menü Verknüpfung der **Test ausführen** Option zum Starten der Animation. Klicken Sie auf **Test beenden** zum Beenden der Animation.  
  
7.  Open **Form1** in der Entwurfsansicht.  
  
8.  Platzieren Sie zwei <xref:System.Windows.Forms.Button> Steuerelemente im Formular. Nennen Sie diese `startButton` und `stopButton`, und ändern Sie die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaftswerte **starten** und **beenden**zugeordnet.  
  
9. Implementieren <xref:System.Windows.Forms.Control.Click> -Ereignishandler für beide <xref:System.Windows.Forms.Button> Steuerelemente.  
  
10. In der **Toolbox**öffnen die **MarqueeControlTest Komponenten** Registerkarte. Daraufhin werden die `DemoMarqueeControl` zur Auswahl zur Verfügung.  
  
11. Ziehen Sie eine Instanz des `DemoMarqueeControl` auf die **Form1** Entwurfsoberfläche angezeigt.  
  
12. In der <xref:System.Windows.Forms.Control.Click> Aufrufen von Ereignishandlern, für die `Start` und `Stop` Methoden für die `DemoMarqueeControl`.  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  Legen Sie die `MarqueeControlTest` -Projekt als Startprojekt aus, und führen Sie sie. Sehen Sie das Formular anzeigen Ihrer `DemoMarqueeControl`. Klicken Sie auf die **starten** Schaltfläche zum Starten der Animation. Blinken Text und die LEDs, um den Rahmen verschieben sollte angezeigt werden.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die `MarqueeControlLibrary` veranschaulicht eine einfache Implementierung von benutzerdefinierten Steuerelementen und zugeordneten Designer. Sie können dieses Beispiel auf verschiedene Weise komplexere vornehmen:  
  
-   Ändern Sie die Eigenschaftswerte für die `DemoMarqueeControl` im Designer. Fügen Sie weitere `MarqueBorder` steuert und Andocken innerhalb ihrer übergeordneten-Instanzen, um einen verschachtelten Effekt zu erstellen. Experimentieren Sie mit unterschiedlichen Einstellungen für die `UpdatePeriod` und die Light-bezogenen Eigenschaften.  
  
-   Erstellen Sie eigene Implementierungen von `IMarqueeWidget`. Sie können z. B. eine blinkende "Neon" oder eine animierte Vorzeichens mit mehrere Abbilder erstellen.  
  
-   Weiter passen Sie an, die zur Entwurfszeit. Sie könnten versuchen, mehr Eigenschaften als shadowing <xref:System.Windows.Forms.Control.Enabled%2A> und <xref:System.Windows.Forms.Control.Visible%2A>, und neue Eigenschaften hinzufügen. Fügen Sie neue Designerverben zur Vereinfachung der häufige Aufgaben wie das Andocken von untergeordneten Steuerelementen.  
  
-   Lizenz der `MarqueeControl`. Weitere Informationen finden Sie unter [Vorgehensweise: Lizenz-Komponenten und Steuerelementen](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).  
  
-   Steuern Sie, wie die Steuerelemente serialisiert werden und wie Code für sie generiert wird. Weitere Informationen finden Sie unter [dynamische Quelle generieren und Kompilieren von](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Entwurfszeitfeatures nutzt](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [Benutzerdefinierte Designer](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [Bibliothek für .NET Form: Eine Beispiel-Designer](http://windowsforms.net/articles/shapedesigner.aspx)
