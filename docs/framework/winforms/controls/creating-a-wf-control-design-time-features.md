---
title: "Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfeatures nutzt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Entwurfszeitfunktionen, Windows Forms"
  - "DocumentDesigner-Klasse [Windows Forms]"
  - "Exemplarische Vorgehensweisen [Windows Forms], Steuerelemente"
  - "Windows Forms-Steuerelemente, Erstellen"
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: 46
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 46
---
# Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfeatures nutzt
Die Entwurfszeiterfahrung für ein benutzerdefiniertes Steuerelement kann verbessert werden, indem ein zugeordneter benutzerdefinierter Designer erstellt wird.  
  
 Diese exemplarische Vorgehensweise veranschaulicht, wie ein benutzerdefinierter Designer für ein benutzerdefiniertes Steuerelement erstellt wird.  Sie implementieren einen `MarqueeControl`\-Typ und eine zugeordnete Designerklasse mit dem Namen `MarqueeControlRootDesigner`.  
  
 Der `MarqueeControl`\-Typ implementiert eine Anzeige, die vergleichbar ist mit einem Theatervordach mit animierten Lichtern und blinkendem Text.  
  
 Der Designer für dieses Steuerelement interagiert mit der Entwurfsumgebung, um eine benutzerdefinierte Entwurfszeiterfahrung bereitzustellen.  Mit dem benutzerdefinierten Designer können Sie eine benutzerdefinierte `MarqueeControl`\-Implementierung mit animierten Lichtern und blinkendem Text in vielen Kombinationen erstellen.  Sie können das erstellte Steuerelement ebenso wie andere Windows Forms\-Steuerelemente auf einem Formular verwenden.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts  
  
-   Erstellen eines Steuerelementbibliothek\-Projekts  
  
-   Verweisen auf das benutzerdefinierte Steuerelementprojekt  
  
-   Definieren eines benutzerdefinierten Steuerelements und seines benutzerdefinierten Designers  
  
-   Erstellen einer Instanz des benutzerdefinierten Steuerelements  
  
-   Einrichten des Projekts zum Entwurfszeitdebuggen  
  
-   Implementieren des benutzerdefinierten Steuerelements  
  
-   Erstellen eines untergeordneten Steuerelements für das benutzerdefinierte Steuerelement  
  
-   Erstellen des untergeordneten MarqueeBorder\-Steuerelements  
  
-   Erstellen eines benutzerdefinierten Designers, um Eigenschaften zu filtern und Shadowing auszuführen  
  
-   Behandeln von Komponentenänderungen  
  
-   Hinzufügen von Designerverben zum benutzerdefinierten Designer  
  
-   Erstellen eines benutzerdefinierten UI\-Typ\-Editors  
  
-   Testen des benutzerdefinierten Steuerelements im Designer  
  
 Zum Schluss sieht das benutzerdefinierte Steuerelement etwa folgendermaßen aus:  
  
 ![Mögliche Anordnung eines MarqueeControl](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")  
  
 Die vollständige Codeliste finden Sie unter [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## Erstellen des Projekts  
 Zunächst muss das Anwendungsprojekt erstellt werden.  Mit diesem Projekt erstellen Sie die Anwendung, die das benutzerdefinierte Steuerelement hostet.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie ein Windows Forms\-Anwendungsprojekt mit dem Namen "MarqueeControlTest". Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
## Erstellen eines Steuerelementbibliothek\-Projekts  
 Der nächste Schritt besteht darin, das Steuerelementbibliothek\-Projekt zu erstellen.  Sie erstellen ein neues benutzerdefiniertes Steuerelement und den entsprechenden benutzerdefinierten Designer.  
  
#### So erstellen Sie das Steuerelementbibliothek\-Projekt  
  
1.  Fügen Sie der Projektmappe ein Windows Forms\-Steuerelementbibliothek\-Projekt hinzu.  Nennen Sie das Projekt "MarqueeControlLibrary".  
  
2.  Löschen Sie im **Projektmappen\-Explorer** das standardmäßige Steuerelement des Projekts, indem Sie die Quelldatei "UserControl1.cs" oder "UserControl1.vb" löschen, je nach ausgewählter Sprache.  Weitere Informationen finden Sie unter [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/de-de/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Fügen Sie dem `MarqueeControlLibrary`\-Projekt ein neues <xref:System.Windows.Forms.UserControl>\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "MarqueeControl" zu.  
  
4.  Erstellen Sie im **Projektmappen\-Explorer** einen neuen Ordner im `MarqueeControlLibrary`\-Projekt.  Weitere Informationen finden Sie unter [NIB:How to: Add New Project Items](http://msdn.microsoft.com/de-de/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  Nennen Sie den neuen Ordner "Design".  
  
5.  Klicken Sie mit der rechten Maustaste auf den Ordner **Design**, und fügen Sie eine neue Klasse hinzu.  Geben Sie der Quelldatei den Basisnamen "MarqueeControlRootDesigner".  
  
6.  Sie müssen Typen aus der System.Design\-Assembly verwenden; fügen Sie also diesen Verweis zum `MarqueeControlLibrary`\-Projekt hinzu.  
  
    > [!NOTE]
    >  Um die System.Design\-Assembly verwenden zu können, muss das Projekt die Vollversion von .NET Framework und nicht das .NET Framework Client Profile als Zielversion verwenden.  Weitere Informationen zum Ändern des Zielframeworks finden Sie unter [Gewusst wie: .NET Framework\-Version als Ziel](../Topic/How%20to:%20Target%20a%20Version%20of%20the%20.NET%20Framework.md).  
  
## Verweisen auf das benutzerdefinierte Steuerelementprojekt  
 Sie verwenden das `MarqueeControlTest`\-Projekt, um das benutzerdefinierte Steuerelement zu testen.  Das Testprojekt erkennt das benutzerdefinierte Steuerelement, wenn Sie der `MarqueeControlLibrary`\-Assembly einen Projektverweis hinzufügen.  
  
#### So verweisen Sie auf das benutzerdefinierte Steuerelementprojekt  
  
-   Fügen Sie im `MarqueeControlTest`\-Projekt der `MarqueeControlLibrary`\-Assembly einen Projektverweis hinzu.  Verwenden Sie die Registerkarte **Projekte** im Dialogfeld **Verweis hinzufügen**, anstatt direkt auf die `MarqueeControlLibrary`\-Assembly zu verweisen.  
  
## Definieren eines benutzerdefinierten Steuerelements und seines benutzerdefinierten Designers  
 Das benutzerdefinierte Steuerelement leitet sich von der <xref:System.Windows.Forms.UserControl>\-Klasse ab.  Dadurch kann es andere Steuerelemente enthalten und erhält einen Großteil der Standardfunktionen.  
  
 Das benutzerdefinierte Steuerelement verfügt über einen zugeordneten benutzerdefinierten Designer.  Dies ermöglicht es Ihnen, einen eindeutigen Entwurfsvorgang zu entwickeln, der speziell an das benutzerdefinierte Steuerelement angepasst ist.  
  
 Sie ordnen das Steuerelement seinem Designer zu, indem Sie die <xref:System.ComponentModel.DesignerAttribute>\-Klasse verwenden.  Da Sie das gesamte Entwurfszeitverhalten des benutzerdefinierten Steuerelements entwickeln, implementiert der benutzerdefinierte Designer die <xref:System.ComponentModel.Design.IRootDesigner>\-Schnittstelle.  
  
#### So definieren Sie ein benutzerdefiniertes Steuerelement und seinen benutzerdefinierten Designer  
  
1.  Öffnen Sie die `MarqueeControl`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei folgende Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  Fügen Sie das <xref:System.ComponentModel.DesignerAttribute> der `MarqueeControl`\-Klassendeklaration hinzu.  Dadurch wird das benutzerdefinierte Steuerelement seinem Designer zugeordnet.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  Öffnen Sie die `MarqueeControlRootDesigner`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei folgende Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  Ändern Sie die Deklaration von `MarqueeControlRootDesigner`, um von der <xref:System.Windows.Forms.Design.DocumentDesigner>\-Klasse zu erben.  Übernehmen Sie <xref:System.ComponentModel.ToolboxItemFilterAttribute>, um die Designerinteraktion mit der **Toolbox** anzugeben.  
  
     **Hinweis** Die Definition für die `MarqueeControlRootDesigner`\-Klasse wurde in einem Namespace mit dem Namen "MarqueeControlLibrary.Design" eingeschlossen. Durch diese Deklaration wird der Designer in einem speziellen Namespace platziert, der für entwurfsbezogene Typen reserviert ist.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  Definieren Sie den Konstruktor für die `MarqueeControlRootDesigner`\-Klasse.  Fügen Sie eine <xref:System.Diagnostics.Trace.WriteLine%2A>\-Anweisung in den Konstruktortext ein.  Diese Vorgehensweise wird zum Debuggen empfohlen.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## Erstellen einer Instanz des benutzerdefinierten Steuerelements  
 Um das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu überprüfen, fügen Sie dem Formular im `MarqueeControlTest`\-Projekt eine Instanz des benutzerdefinierten Steuerelements hinzu.  
  
#### So erstellen Sie eine Instanz des benutzerdefinierten Steuerelements  
  
1.  Fügen Sie dem `MarqueeControlTest`\-Projekt ein neues <xref:System.Windows.Forms.UserControl>\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "DemoMarqueeControl" zu.  
  
2.  Öffnen Sie die `DemoMarqueeControl`\-Datei im **Code\-Editor**.  Importieren Sie am Anfang der Datei den `MarqueeControlLibrary`\-Namespace:  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  Ändern Sie die Deklaration von `DemoMarqueeControl`, um von der `MarqueeControl`\-Klasse zu erben.  
  
2.  Erstellen Sie das Projekt.  
  
3.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
4.  Öffnen Sie in der **Toolbox** die Registerkarte **MarqueeControlTest\-Komponenten**.  Ziehen Sie ein `DemoMarqueeControl` aus der **Toolbox** auf das Formular.  
  
5.  Erstellen Sie das Projekt.  
  
## Einrichten des Projekts zum Entwurfszeitdebuggen  
 Wenn Sie eine benutzerdefinierte Entwurfszeiterfahrung entwickeln, müssen Sie die Steuerelemente und Komponenten debuggen.  Es gibt eine einfache Möglichkeit, das Projekt zum Entwurfszeitdebuggen einzurichten.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
#### So richten Sie das Projekt zum Entwurfszeitdebuggen ein  
  
1.  Klicken Sie mit der rechten Maustaste auf das `MarqueeControlLibrary`\-Projekt, und wählen Sie **Eigenschaften**.  
  
2.  Wählen Sie im Dialogfeld "MarqueeControlLibrary\-Eigenschaftenseiten" die Seite **Debuggen** aus.  
  
3.  Wählen Sie im Abschnitt **Startaktion** die Option **Externes Programm starten** aus.  Da Sie eine separate Instanz von Visual Studio debuggen, klicken Sie auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um nach der Visual Studio IDE zu suchen.  Der Name der ausführbaren Datei lautet devenv.exe. Bei der Installation am Standardspeicherort lautet der Pfad %programfiles%\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe.  
  
4.  Klicken Sie auf OK, um das Dialogfeld zu schließen.  
  
5.  Klicken Sie mit der rechten Maustaste auf das `MarqueeControlLibrary`\-Projekt, und wählen Sie "Als Startprojekt festlegen" aus, um diese Debugkonfiguration zu aktivieren.  
  
## Checkpoint  
 Sie sind nun bereit, das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu debuggen.  Nachdem Sie sichergestellt haben, dass die Debugumgebung ordnungsgemäß eingerichtet wurde, testen Sie die Zuordnung zwischen dem benutzerdefinierten Steuerelement und dem benutzerdefinierten Designer.  
  
#### So testen Sie die Debugumgebung und die Designerzuordnung  
  
1.  Öffnen Sie die Quelldatei `MarqueeControlRootDesigner` im **Code\-Editor**, und platzieren Sie auf der <xref:System.Diagnostics.Trace.WriteLine%2A>\-Anweisung einen Haltepunkt.  
  
2.  Drücken Sie F5, um die Debugsitzung zu starten.  Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.  
  
3.  Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "MarqueeControlTest".  Sie können die Projektmappe leicht finden, indem Sie im Menü **Datei** die Option **Zuletzt geöffnete Projekte** auswählen.  Die Projektmappendatei "MarqueeControlTest.sln" wird als zuletzt verwendete Datei aufgelistet.  
  
4.  Öffnen Sie das `DemoMarqueeControl` im Designer.  Beachten Sie, dass die Debuginstanz von Visual Studio aktiviert und die Ausführung am Haltepunkt beendet wird.  Drücken Sie F5, um die Debugsitzung fortzusetzen.  
  
 An diesem Punkt können Sie damit beginnen, das benutzerdefinierte Steuerelement und seinen zugeordneten Designer zu entwickeln und zu debuggen.  Im restlichen Teil dieser exemplarischen Vorgehensweise werden in erster Linie die Details der Implementierung von Features für das Steuerelement und den Designer erläutert.  
  
## Implementieren des benutzerdefinierten Steuerelements  
 Das `MarqueeControl` ist ein <xref:System.Windows.Forms.UserControl>, für das geringfügige Anpassungen erforderlich sind.  Es macht zwei Methoden verfügbar: `Start` startet die Animation, und `Stop` beendet die Animation.  Da das `MarqueeControl` untergeordnete Steuerelemente enthält, die die `IMarqueeWidget`\-Schnittstelle implementieren, listen `Start` und `Stop` jedes untergeordnete Steuerelement auf und rufen die `StartMarquee`\-Methode bzw. die `StopMarquee`\-Methode zu jedem untergeordneten Element auf, das `IMarqueeWidget` implementiert.  
  
 Das Aussehen des `MarqueeBorder`\-Steuerelements und des `MarqueeText`\-Steuerelements hängt vom Layout ab, d. h., `MarqueeControl` überschreibt die <xref:System.Windows.Forms.Control.OnLayout%2A>\-Methode und ruft zu untergeordneten Steuerelementen dieses Typs <xref:System.Windows.Forms.Control.PerformLayout%2A> auf.  
  
 Dies sind alle für das `MarqueeControl` erforderlichen Anpassungen.  Die Laufzeitfeatures werden von dem `MarqueeBorder`\-Steuerelement und dem `MarqueeText`\-Steuerelement implementiert, und die Entwurfszeitfeatures werden von der `MarqueeBorderDesigner`\-Klasse und der `MarqueeControlRootDesigner`\-Klasse implementiert.  
  
#### So implementieren Sie das benutzerdefinierte Steuerelement  
  
1.  Öffnen Sie die `MarqueeControl`\-Quelldatei im **Code\-Editor**.  Implementieren Sie die `Start`\-Methode und die `Stop`\-Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  Überschreiben der <xref:System.Windows.Forms.Control.OnLayout%2A>\-Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## Erstellen eines untergeordneten Steuerelements für das benutzerdefinierte Steuerelement  
 Das `MarqueeControl` hostet zwei Arten von untergeordnetem Steuerelementen: das `MarqueeBorder`\-Steuerelement und das `MarqueeText`\-Steuerelement.  
  
-   `MarqueeBorder`: Dieses Steuerelement zeichnet einen Rahmen mit "Lichtern" um seine Kanten.  Die Lichter blinken nacheinander auf, als würden Sie um den Rahmen herum wandern.  Die Geschwindigkeit, mit der die Lichter aufblinken, wird von einer Eigenschaft mit dem Namen `UpdatePeriod` gesteuert.  Mehrere andere benutzerdefinierte Eigenschaften bestimmen weitere Aspekte der Darstellung des Steuerelements.  Zwei Methoden, nämlich `StartMarquee` und `StopMarquee`, steuern, wann die Animation startet und anhält.  
  
-   `MarqueeText`: Dieses Steuerelement zeichnet eine aufblinkende Zeichenfolge.  Wie beim `MarqueeBorder`\-Steuerelement wird die Geschwindigkeit, mit der der Text aufblinkt, von der `UpdatePeriod`\-Eigenschaft gesteuert.  Außerdem verfügt das `MarqueeText`\-Steuerelement wie das `MarqueeBorder`\-Steuerelement über die `StartMarquee`\-Methode und die `StopMarquee`\-Methode.  
  
 Zur Entwurfszeit ermöglicht der `MarqueeControlRootDesigner`, dass diese beiden Steuerelementtypen in jeder beliebigen Kombination einem `MarqueeControl` hinzugefügt werden.  
  
 Allgemeine Features der beiden Steuerelemente werden auf eine Schnittstelle mit dem Namen `IMarqueeWidget` aufgeteilt.  Dies ermöglicht es dem `MarqueeControl`, Marquee\-verwandte untergeordnete Steuerelemente zu ermitteln und sie besonders zu behandeln.  
  
 Um das periodische Animationsfeature zu implementieren, verwenden Sie <xref:System.ComponentModel.BackgroundWorker>\-Objekte vom <xref:System.ComponentModel?displayProperty=fullName>\-Namespace.  Sie könnten <xref:System.Windows.Forms.Timer>\-Objekte verwenden, aber bei mehreren `IMarqueeWidget`\-Objekten ist der einzelne UI\-Thread möglicherweise nicht in der Lage, die Animation zu verarbeiten.  
  
#### So erstellen Sie ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement  
  
1.  Fügen Sie dem `MarqueeControlLibrary`\-Projekt ein neues Klassenelement hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "IMarqueeWidget" zu.  
  
2.  Öffnen Sie die Quelldatei `IMarqueeWidget` im **Code\-Editor**, und ändern Sie die Deklaration von `class` in `interface`:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  Fügen Sie folgenden Code zur `IMarqueeWidget`\-Schnittstelle hinzu, um zwei Methoden und eine Eigenschaft verfügbar zu machen, mit denen die Animation bearbeitet wird:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  Fügen Sie dem `MarqueeControlLibrary`\-Projekt ein neues **Benutzerdefiniertes Steuerelement**\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "MarqueeText" zu.  
  
5.  Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker>\-Komponente aus der **Toolbox** auf das `MarqueeText`\-Steuerelement.  Diese Komponente ermöglicht es dem `MarqueeText`\-Steuerelement, sich asynchron zu aktualisieren.  
  
6.  Legen Sie im Eigenschaftenfenster die `WorkerReportsProgess`\-Eigenschaft und die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>\-Eigenschaft der <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf `true` fest.  Diese Einstellungen ermöglichen es der <xref:System.ComponentModel.BackgroundWorker>\-Komponente, das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis periodisch auszulösen und asynchrone Aktualisierungen abzubrechen.  Weitere Informationen hierzu finden Sie unter [BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
7.  Öffnen Sie die `MarqueeText`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei folgende Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  Ändern Sie die Deklaration von `MarqueeText`, um von <xref:System.Windows.Forms.Label> zu erben und die `IMarqueeWidget`\-Schnittstelle zu implementieren:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie sie im Konstruktor.  Das `isLit`\-Feld legt fest, ob der Text in der von der `LightColor`\-Eigenschaft vorgegebenen Farbe gezeichnet wird.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. Implementieren Sie die `IMarqueeWidget`\-Schnittstelle.  
  
     Die `StartMarquee`\-Methode und die `StopMarquee`\-Methode rufen die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode und die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>\-Methode der <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf, um die Animation zu starten und zu stoppen.  
  
     Das <xref:System.ComponentModel.CategoryAttribute.Category%2A>\-Attribut und das <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>\-Attribut werden auf die `UpdatePeriod`\-Eigenschaft angewendet, sodass diese in einem benutzerdefinierten Abschnitt des Eigenschaftenfensters mit dem Namen "Marquee" angezeigt wird.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. Implementieren Sie die Eigenschaftenaccessoren.  Sie machen Clients zwei Eigenschaften verfügbar: `LightColor` und `DarkColor`.  Das <xref:System.ComponentModel.CategoryAttribute.Category%2A>\-Attribut und das <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>\-Attribut werden auf diese Eigenschaften angewendet, sodass die Eigenschaften in einem benutzerdefinierten Abschnitt des Eigenschaftenfensters mit dem Namen "Marquee" angezeigt werden.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis und das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis der <xref:System.ComponentModel.BackgroundWorker>\-Komponente.  
  
     Der <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler ruht für die durch `UpdatePeriod` festgelegte Anzahl an Millisekunden und löst anschließend das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis aus, bis der Code die Animation durch Aufrufen von <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> beendet.  
  
     Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignishandler schaltet den Zustand des Textes von hell in dunkel und umgekehrt um, sodass der Anschein entsteht, dass dieser aufblinkt.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, um die Animation zu aktivieren.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. Drücken Sie F6, um die Projektmappe zu erstellen.  
  
## Erstellen des untergeordneten MarqueeBorder\-Steuerelements  
 Das `MarqueeBorder`\-Steuerelement ist etwas raffinierter als das `MarqueeText`\-Steuerelement.  Es verfügt über mehr Eigenschaften, und die Animation in der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode ist komplizierter.  Im Prinzip ist es mit dem `MarqueeText`\-Steuerelement vergleichbar.  
  
 Da das `MarqueeBorder`\-Steuerelement über untergeordnete Steuerelemente verfügen kann, muss es <xref:System.Windows.Forms.Control.Layout>\-Ereignisse berücksichtigen.  
  
#### So erstellen Sie das MarqueeBorder\-Steuerelement  
  
1.  Fügen Sie dem `MarqueeControlLibrary`\-Projekt ein neues **Benutzerdefiniertes Steuerelement**\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "MarqueeBorder" zu.  
  
2.  Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker>\-Komponente aus der **Toolbox** auf das `MarqueeBorder`\-Steuerelement.  Diese Komponente ermöglicht es dem `MarqueeBorder`\-Steuerelement, sich asynchron zu aktualisieren.  
  
3.  Legen Sie im Eigenschaftenfenster die `WorkerReportsProgess`\-Eigenschaft und die <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A>\-Eigenschaft der <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf `true` fest.  Diese Einstellungen ermöglichen es der <xref:System.ComponentModel.BackgroundWorker>\-Komponente, das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis periodisch auszulösen und asynchrone Aktualisierungen abzubrechen.  Weitere Informationen hierzu finden Sie unter [BackgroundWorker\-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component.md).  
  
4.  Klicken Sie im Fenster Eigenschaften auf die Schaltfläche Ereignisse.  Fügen Sie Handler für die <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignisse und die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignisse an.  
  
5.  Öffnen Sie die `MarqueeBorder`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei folgende Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  Ändern Sie die Deklaration von `MarqueeBorder`, um von <xref:System.Windows.Forms.Panel> zu erben und die `IMarqueeWidget`\-Schnittstelle zu implementieren.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  Deklarieren Sie zwei Enumerationen, um den Zustand des `MarqueeBorder`\-Steuerelements zu verwalten: `MarqueeSpinDirection` bestimmt die Richtung, in die die Lichter um den Rand herum wandern, und `MarqueeLightShape` bestimmt die Form der Lichter \(quadratisch oder rund\).  Platzieren Sie diese Deklarationen vor der `MarqueeBorder`\-Klassendeklaration.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie sie im Konstruktor.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. Implementieren Sie die `IMarqueeWidget`\-Schnittstelle.  
  
     Die `StartMarquee`\-Methode und die `StopMarquee`\-Methode rufen die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>\-Methode und die <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>\-Methode der <xref:System.ComponentModel.BackgroundWorker>\-Komponente auf, um die Animation zu starten und zu stoppen.  
  
     Da das `MarqueeBorder`\-Steuerelement untergeordnete Steuerelemente enthalten kann, listet die `StartMarquee`\-Methode alle untergeordneten Steuerelemente auf und ruft `StartMarquee` für diejenigen auf, die `IMarqueeWidget` implementieren.  Die `StopMarquee`\-Methode verfügt über eine ähnliche Implementierung.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. Implementieren Sie die Eigenschaftenaccessoren.  Das `MarqueeBorder`\-Steuerelement verfügt über mehrere Eigenschaften, die sein Aussehen steuern.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignis und das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis der <xref:System.ComponentModel.BackgroundWorker>\-Komponente.  
  
     Der <xref:System.ComponentModel.BackgroundWorker.DoWork>\-Ereignishandler ruht für die durch `UpdatePeriod` festgelegte Anzahl an Millisekunden und löst anschließend das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignis aus, bis der Code die Animation durch Aufrufen von <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> beendet.  
  
     Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>\-Ereignishandler erhöht die Position des "Basislichts", durch die der Hell\-\/Dunkelzustand der anderen Lichter bestimmt wird, und ruft die <xref:System.Windows.Forms.Control.Refresh%2A>\-Methode auf, damit das Steuerelement sich selbst neu zeichnet.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. Implementieren Sie die Hilfemethoden `IsLit` und `DrawLight`.  
  
     Die `IsLit`\-Methode bestimmt die Farbe eines Lichts an einer bestimmten Position.  Helle Lichter werden in der durch die `LightColor`\-Eigenschaft vorgegebenen Farbe gezeichnet, während dunkle Farben in der durch die `DarkColor`\-Eigenschaft vorgegebenen Farbe gezeichnet werden.  
  
     Die `DrawLight`\-Methode zeichnet ein Licht mit der entsprechenden Farbe, Form und Position.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A>\-Methode und die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode.  
  
     Die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode zeichnet die Lichter an den Rändern des `MarqueeBorder`\-Steuerelements.  
  
     Da die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode von den Maßen des `MarqueeBorder`\-Steuerelements abhängt, müssen Sie sie aufrufen, sobald sich das Layout ändert.  Hierfür überschreiben Sie <xref:System.Windows.Forms.Control.OnLayout%2A> und rufen <xref:System.Windows.Forms.Control.Refresh%2A> auf.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## Erstellen eines benutzerdefinierten Designers, um Eigenschaften zu filtern und Shadowing auszuführen  
 Die `MarqueeControlRootDesigner`\-Klasse stellt die Implementierung für den Stamm\-Designer bereit.  Neben diesem Designer, der auf das `MarqueeControl` angewendet wird, benötigen Sie einen benutzerdefinierten Designer, der speziell dem `MarqueeBorder`\-Steuerelement zugeordnet ist.  Dieser Designer stellt benutzerdefiniertes Verhalten bereit, das im Hinblick auf den benutzerdefinierten Stamm\-Designer angemessen ist.  
  
 Insbesondere der `MarqueeBorderDesigner` filtert bestimmte Eigenschaften des `MarqueeBorder`\-Steuerelements und führt für diese Shadowing aus, wodurch sich die Interaktion mit der Entwurfsumgebung ändert.  
  
 Unter Shadowing versteht man das Abfangen von Aufrufen an den Eigenschaftenaccessor einer Komponente. Es ermöglicht einem Designer, den vom Benutzer festgelegten Wert zu verfolgen und optional diesen Wert an die Komponente zu übergeben, die entworfen wird.  
  
 In diesem Beispiel wird für die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.Enabled%2A>\-Eigenschaft vom `MarqueeBorderDesigner` ein Shadowing ausgeführt. Dadurch wird der Benutzer daran gehindert, das `MarqueeBorder`\-Steuerelement zur Entwurfszeit unsichtbar zu machen oder zu deaktivieren.  
  
 Designer können zudem Eigenschaften hinzufügen und entfernen.  In diesem Beispiel wird die <xref:System.Windows.Forms.Control.Padding%2A>\-Eigenschaft zur Entwurfszeit entfernt, da das `MarqueeBorder`\-Steuerelement den Abstand programmgesteuert anhand der Größe der Lichter festlegt, die von der `LightSize`\-Eigenschaft vorgegeben ist.  
  
 Die Basisklasse für `MarqueeBorderDesigner` ist <xref:System.ComponentModel.Design.ComponentDesigner>. Diese verfügt über Methoden, die die Attribute, Eigenschaften und Ereignisse ändern können, die zur Entwurfszeit von einem Steuerelement verfügbar gemacht werden.  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 Wenn Sie die öffentliche Schnittstelle einer Komponente mithilfe dieser Methoden ändern, müssen Sie die folgenden Regeln beachten:  
  
-   Verwenden Sie ausschließlich die `PreFilter`\-Methoden, um Elemente hinzuzufügen oder zu entfernen.  
  
-   Ändern Sie vorhandene Elemente ausschließlich in den `PostFilter`\-Methoden.  
  
-   Rufen Sie immer zuerst die Basisimplementierung in den `PreFilter`\-Methoden auf.  
  
-   Rufen Sie immer zuletzt die Basisimplementierung in den `PostFilter`\-Methoden auf.  
  
 Wenn Sie diese Regeln beachten, wird sichergestellt, dass alle Designer in der Entwurfszeitumgebung über eine konsistente Ansicht der zu entwerfenden Komponenten verfügen.  
  
 Die <xref:System.ComponentModel.Design.ComponentDesigner>\-Klasse stellt ein Wörterbuch zur Verwaltung der Werte von Eigenschaften zur Verfügung, für die ein Shadowing ausgeführt wurde, sodass Sie keine bestimmten Instanzenvariablen erstellen müssen.  
  
#### So erstellen Sie einen benutzerdefinierten Designer, um Eigenschaften zu filtern und Shadowing durchzuführen  
  
1.  Klicken Sie mit der rechten Maustaste auf den Ordner **Design**, und fügen Sie eine neue Klasse hinzu.  Geben Sie der Quelldatei den Basisnamen "MarqueeBorderDesigner".  
  
2.  Öffnen Sie die `MarqueeBorderDesigner`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei folgende Namespaces:  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  Ändern Sie die Deklaration von `MarqueeBorderDesigner`, um von <xref:System.Windows.Forms.Design.ParentControlDesigner> zu erben.  
  
     Da das `MarqueeBorder`\-Steuerelement untergeordnete Steuerelemente enthalten kann, erbt `MarqueeBorderDesigner` von <xref:System.Windows.Forms.Design.ParentControlDesigner>, der die Interaktion zwischen übergeordneten und untergeordneten Elementen behandelt.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  Überschreiben Sie die Basisimplementierung von <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  Implementieren Sie die <xref:System.Windows.Forms.Control.Enabled%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.Visible%2A>\-Eigenschaft.  Diese Implementierungen führen für die Eigenschaften des Steuerelements ein Shadowing aus.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## Behandeln von Komponentenänderungen  
 Die `MarqueeControlRootDesigner`\-Klasse stellt die benutzerdefinierte Entwurfszeiterfahrung für die `MarqueeControl`\-Instanzen bereit.  Die meisten Entwurfszeitfunktionen werden von der <xref:System.Windows.Forms.Design.DocumentDesigner>\-Klasse geerbt. Der Code implementiert zwei spezielle Anpassungen: das Behandeln von Komponentenänderungen und das Hinzufügen von Designerverben.  
  
 Da Benutzer die `MarqueeControl`\-Instanzen entwerfen, verfolgt der Stamm\-Designer Änderungen am `MarqueeControl` und an dessen untergeordneten Steuerelementen nach.  Die Entwurfszeitumgebung bietet einen praktischen Dienst, den <xref:System.ComponentModel.Design.IComponentChangeService>, um Änderungen am Komponentenzustand zu verfolgen.  
  
 Sie erhalten einen Verweis auf diesen Dienst, indem Sie die Umgebung mit der <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>\-Methode abfragen.  Wenn die Abfrage erfolgreich ist, kann der Designer einen Handler für das <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged>\-Ereignis zuordnen und alle Aufgaben ausführen, die zur Erhaltung eines konsistenten Zustands zur Entwurfszeit erforderlich sind.  
  
 Bei einer `MarqueeControlRootDesigner`\-Klasse rufen Sie die <xref:System.Windows.Forms.Control.Refresh%2A>\-Methode für jedes `IMarqueeWidget`\-Objekt auf, das im `MarqueeControl` enthalten ist.  Dies bewirkt, dass das `IMarqueeWidget`\-Objekt sich entsprechend neu zeichnet, wenn sich Eigenschaften wie die <xref:System.Windows.Forms.Control.Size%2A> des übergeordneten Elements ändern.  
  
#### So behandeln Sie Komponentenänderungen  
  
1.  Öffnen Sie die Quelldatei `MarqueeControlRootDesigner` im **Code\-Editor**, und überschreiben Sie die <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>\-Methode.  Rufen Sie die Basisimplementierung von <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> auf, und fragen Sie den <xref:System.ComponentModel.Design.IComponentChangeService> ab.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  Implementieren Sie den <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>\-Ereignishandler.  Testen Sie den Typ der sendenden Komponente. Wenn es sich um `IMarqueeWidget` handelt, rufen Sie die entsprechende <xref:System.Windows.Forms.Control.Refresh%2A>\-Methode auf.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## Hinzufügen von Designerverben zum benutzerdefinierten Designer  
 Ein Designerverb ist ein mit einem Ereignishandler verknüpfter Menübefehl.  Designerverben werden zur Entwurfszeit dem Kontextmenü einer Komponente hinzugefügt.  Weitere Informationen finden Sie unter <xref:System.ComponentModel.Design.DesignerVerb>.  
  
 Sie fügen den Designern zwei Designerverben hinzu: **Test ausführen** und **Test beenden**.  Diese Verben ermöglichen es Ihnen, das Laufzeitverhalten des `MarqueeControl` zur Entwurfszeit anzuzeigen.  Diese Verben werden dem `MarqueeControlRootDesigner` hinzugefügt.  
  
 Wenn **Test ausführen** aufgerufen wird, ruft der Verbereignishandler die `StartMarquee`\-Methode für das `MarqueeControl` auf.  Wenn **Test beenden** aufgerufen wird, ruft der Verbereignishandler die `StopMarquee`\-Methode für das `MarqueeControl` auf.  Die Implementierung der `StartMarquee`\-Methode und der `StopMarquee`\-Methode bewirkt, dass diese Methoden für enthaltene Steuerelemente aufgerufen werden, die `IMarqueeWidget` implementieren, sodass jedes enthaltene `IMarqueeWidget`\-Steuerelement im Test berücksichtigt wird.  
  
#### So fügen Sie Designerverben den benutzerdefinierten Designern hinzu  
  
1.  Fügen Sie in der `MarqueeControlRootDesigner`\-Klasse Ereignishandler mit den Namen `OnVerbRunTest` und `OnVerbStopTest` hinzu.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  Verbinden Sie diese Ereignishandler mit den entsprechenden Designerverben.  `MarqueeControlRootDesigner` erbt von der <xref:System.ComponentModel.Design.DesignerVerbCollection>\-Basisklasse.  Sie erstellen zwei neue <xref:System.ComponentModel.Design.DesignerVerb>\-Objekte und fügen sie dieser Auflistung in der <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>\-Methode hinzu.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## Erstellen eines benutzerdefinierten UI\-Typ\-Editors  
 Wenn Sie eine benutzerdefinierte Entwurfszeiterfahrung für Benutzer erstellen, ist es häufig angebracht, eine benutzerdefinierte Interaktion mit dem Eigenschaftenfenster zu erstellen.  Hierzu können Sie einen <xref:System.Drawing.Design.UITypeEditor> erstellen.  Weitere Informationen finden Sie unter [How to: Create a UI Type Editor](../Topic/How%20to:%20Create%20a%20UI%20Type%20Editor.md).  
  
 Das `MarqueeBorder`\-Steuerelement macht mehrere Eigenschaften im Eigenschaftenfenster verfügbar.  Zwei von diesen Eigenschaften, `MarqueeSpinDirection` und `MarqueeLightShape`, werden durch Enumerationen dargestellt.  Um die Verwendung eines UI\-Typ\-Editors zu veranschaulichen, verfügt die `MarqueeLightShape`\-Eigenschaft über eine zugehörige <xref:System.Drawing.Design.UITypeEditor>\-Klasse.  
  
#### So erstellen Sie einen benutzerdefinierten UI\-Typ\-Editor  
  
1.  Öffnen Sie die `MarqueeBorder`\-Quelldatei im **Code\-Editor**.  
  
2.  Deklarieren Sie in der Definition der `MarqueeBorder`\-Klasse eine Klasse mit dem Namen `LightShapeEditor`, die sich von <xref:System.Drawing.Design.UITypeEditor> ableitet.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>\-Instanzvariable mit der Bezeichnung `editorService`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  Überschreiben der <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>\-Methode.  Diese Implementierung gibt <xref:System.Drawing.Design.UITypeEditorEditStyle> zurück und weist die Entwurfsumgebung an, wie der `LightShapeEditor` angezeigt werden soll.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  Überschreiben der <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>\-Methode.  Diese Implementierung fragt ein <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>\-Objekt aus der Entwurfsumgebung ab.  Wenn die Abfrage erfolgreich ist, wird ein `LightShapeSelectionControl` erstellt.  Die <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>\-Methode wird aufgerufen, um den `LightShapeEditor` zu starten.  Der Rückgabewert von diesem Aufruf wird an die Entwurfsumgebung zurückgegeben.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## Erstellen eines Ansichtssteuerelements für den benutzerdefinierten UI\-Typ\-Editor  
  
1.  Die `MarqueeLightShape`\-Eigenschaft unterstützt zwei Typen von Lichterformen: `Square` und `Circle`.  Sie erstellen ein benutzerdefiniertes Steuerelement, das ausschließlich zur Anzeige dieser Werte im Eigenschaftenfenster dient.  Dieses benutzerdefinierte Steuerelement wird vom <xref:System.Drawing.Design.UITypeEditor> zur Interaktion mit dem Eigenschaftenfenster verwendet.  
  
#### So erstellen Sie ein Ansichtssteuerelement für den benutzerdefinierten UI\-Typ\-Editor  
  
1.  Fügen Sie dem `MarqueeControlLibrary`\-Projekt ein neues <xref:System.Windows.Forms.UserControl>\-Element hinzu.  Weisen Sie der neuen Quelldatei den Basisnamen "LightShapeSelectionControl" zu.  
  
2.  Ziehen Sie zwei <xref:System.Windows.Forms.Panel>\-Steuerelemente aus der **Toolbox** auf das `LightShapeSelectionControl`.  Nennen Sie sie `squarePanel` und `circlePanel`.  Ordnen Sie sie nebeneinander an.  Legen Sie die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft beider <xref:System.Windows.Forms.Panel>\-Steuerelemente auf \(60, 60\) fest.  Legen Sie die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft des `squarePanel`\-Steuerelements auf \(8, 10\) fest.  Legen Sie die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft des `circlePanel`\-Steuerelements auf \(80, 10\) fest.  Legen Sie zuletzt die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft des `LightShapeSelectionControl` auf \(150, 80\) fest.  
  
3.  Öffnen Sie die `LightShapeSelectionControl`\-Quelldatei im **Code\-Editor**.  Importieren Sie am Anfang der Datei den <xref:System.Windows.Forms.Design?displayProperty=fullName>\-Namespace:  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  Implementieren Sie <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für das `squarePanel`\-Steuerelement und das `circlePanel`\-Steuerelement.  Diese Methoden rufen <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> auf, um die benutzerdefinierte <xref:System.Drawing.Design.UITypeEditor>\-Bearbeitungssitzung zu beenden.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService>\-Instanzvariable mit der Bezeichnung `editorService`.  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  Deklarieren Sie eine `MarqueeLightShape`\-Instanzvariable mit der Bezeichnung `lightShapeValue`.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  Fügen Sie im `LightShapeSelectionControl`\-Konstruktor die <xref:System.Windows.Forms.Control.Click>\-Ereignishandler an die <xref:System.Windows.Forms.Control.Click>\-Ereignisse des `squarePanel`\-Steuerelements und des `circlePanel`\-Steuerelements an.  Definieren Sie darüber hinaus auch eine Konstruktorüberladung, die dem `lightShapeValue`\-Feld den `MarqueeLightShape`\-Wert aus der Entwurfsumgebung zuweist.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  Trennen Sie die <xref:System.Windows.Forms.Control.Click>\-Ereignishandler in der <xref:System.ComponentModel.Component.Dispose%2A>\-Methode.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  Klicken Sie im **Projektmappen\-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  Öffnen Sie die Datei LightShapeSelectionControl.Designer.cs oder die Datei LightShapeSelectionControl.Designer.vb, und entfernen Sie die Standarddefinition der <xref:System.ComponentModel.Component.Dispose%2A>\-Methode.  
  
5.  Implementieren Sie die `LightShape`\-Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode.  Mit dieser Implementierung wird ein ausgefülltes Quadrat und ein ausgefüllter Kreis gezeichnet.  Zudem wird der ausgewählte Wert durch Zeichnen eines Rahmens um eine der Formen hervorgehoben.  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## Testen des benutzerdefinierten Steuerelements im Designer  
 Sie können nun das `MarqueeControlLibrary`\-Projekt erstellen.  Testen Sie die Implementierung, indem Sie ein Steuerelement erstellen, das von der `MarqueeControl`\-Klasse erbt, und dieses auf einem Formular verwenden.  
  
#### So erstellen Sie eine benutzerdefinierte MarqueeControl\-Implementierung  
  
1.  Öffnen Sie `DemoMarqueeControl` im Windows Forms\-Designer.  Hierdurch wird eine Instanz des `DemoMarqueeControl`\-Typs erstellt und in einer Instanz des `MarqueeControlRootDesigner`\-Typs angezeigt.  
  
2.  Öffnen Sie in der **Toolbox** die Registerkarte **MarqueeControlLibrary\-Komponenten**.  Das `MarqueeBorder`\-Steuerelement und das `MarqueeText`\-Steuerelement werden angezeigt und können ausgewählt werden.  
  
3.  Ziehen Sie eine Instanz des `MarqueeBorder`\-Steuerelements auf die `DemoMarqueeControl`\-Entwurfsoberfläche.  Docken Sie dieses `MarqueeBorder`\-Steuerelement am übergeordneten Steuerelement an.  
  
4.  Ziehen Sie eine Instanz des `MarqueeText`\-Steuerelements auf die `DemoMarqueeControl`\-Entwurfsoberfläche.  
  
5.  Erstellen Sie die Projektmappe.  
  
6.  Klicken Sie mit der rechten Maustaste auf `DemoMarqueeControl`. Wählen Sie im Kontextmenü die Option **Test ausführen** aus, um die Animation zu starten.  Klicken Sie auf **Test beenden**, um die Animation zu beenden.  
  
7.  Öffnen Sie **Form1** in der Entwurfsansicht.  
  
8.  Platzieren Sie zwei <xref:System.Windows.Forms.Button>\-Steuerelemente auf dem Formular.  Nennen Sie die Steuerelemente `startButton` und `stopButton`, und ändern Sie die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaftswerte in Start bzw. Stop.  
  
9. Implementieren Sie <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für beide <xref:System.Windows.Forms.Button>\-Steuerelemente.  
  
10. Öffnen Sie in der **Toolbox** die Registerkarte **MarqueeControlTest\-Komponenten**.  Das `DemoMarqueeControl` wird angezeigt und kann ausgewählt werden.  
  
11. Ziehen Sie eine Instanz des `DemoMarqueeControl` auf die **Form1**\-Entwurfsoberfläche.  
  
12. Rufen Sie in den <xref:System.Windows.Forms.Control.Click>\-Ereignishandlern die `Start`\-Methode und die `Stop`\-Methode für das `DemoMarqueeControl` auf.  
  
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
  
1.  Legen Sie das `MarqueeControlTest`\-Projekt als Startprojekt fest, und führen Sie es aus.  Im Formular wird Ihr `DemoMarqueeControl` angezeigt.  Klicken Sie auf die Schaltfläche **Start**, um die Animation zu starten.  Der Text sollte blinken, und die Lichter bewegen sich am Rand entlang.  
  
## Nächste Schritte  
 Die `MarqueeControlLibrary` veranschaulicht eine einfache Implementierung von benutzerdefinierten Steuerelementen und zugehörigen Designern.  Sie können dieses Beispiel auf verschiedene Weise anspruchsvoller gestalten:  
  
-   Ändern Sie die Eigenschaftswerte für das `DemoMarqueeControl` im Designer.  Fügen Sie weitere `MarqueBorder`\-Steuerelemente hinzu, und docken Sie sie innerhalb ihrer übergeordneten Instanzen an, um einen verschachtelten Effekt zu erstellen.  Probieren Sie andere Einstellungen für die `UpdatePeriod` und die Lichteigenschaften aus.  
  
-   Erstellen Sie Ihre eigenen Implementierungen von `IMarqueeWidget`.  Sie könnten beispielsweise eine aufblinkende "Leuchtreklame" oder ein animiertes Symbol mit mehreren Bildern erstellen.  
  
-   Passen Sie die Entwurfszeiterfahrung weiter an.  Sie könnten versuchen, für mehr Eigenschaften als <xref:System.Windows.Forms.Control.Enabled%2A> und <xref:System.Windows.Forms.Control.Visible%2A> ein Shadowing auszuführen, und Sie könnten neue Eigenschaften hinzufügen.  Fügen Sie neue Designerverben hinzu, um häufige Aufgaben zu vereinfachen, z. B. das Andocken von untergeordneten Steuerelementen.  
  
-   Lizenzieren Sie das `MarqueeControl`.  Weitere Informationen finden Sie unter [How to: License Components and Controls](../Topic/How%20to:%20License%20Components%20and%20Controls.md).  
  
-   Steuern Sie, wie die Steuerelemente serialisiert werden und wie Code für sie generiert wird.  Weitere Informationen finden Sie unter [Generieren und Kompilieren von dynamischem Quellcode](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Design.ParentControlDesigner>   
 <xref:System.Windows.Forms.Design.DocumentDesigner>   
 <xref:System.ComponentModel.Design.IRootDesigner>   
 <xref:System.ComponentModel.Design.DesignerVerb>   
 <xref:System.Drawing.Design.UITypeEditor>   
 <xref:System.ComponentModel.BackgroundWorker>   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Custom Designers](../Topic/Custom%20Designers.md)   
 [.NET\-Shape\-Bibliothek: Beispiel\-Designer](http://windowsclient.net/)