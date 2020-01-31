---
title: Erstellen eines Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7166b4203c54ab31f1d929c85cf1e6481ff120f8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744078"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Exemplarische Vorgehensweise: Erstellen eines Steuer Elements, das Entwurfszeit Features nutzt

Die Entwurfszeit Darstellung eines benutzerdefinierten Steuer Elements kann durch die Erstellung eines zugeordneten benutzerdefinierten Designers verbessert werden.

Dieser Artikel veranschaulicht das Erstellen eines benutzerdefinierten Designers für ein benutzerdefiniertes Steuerelement. Sie implementieren einen `MarqueeControl` Typ und eine zugehörige Designer Klasse mit dem Namen `MarqueeControlRootDesigner`.

Der `MarqueeControl` Typ implementiert eine Anzeige ähnlich einem Theater-Marquee mit animierten Lichtern und blinkenden Text.

Der Designer für dieses Steuerelement interagiert mit der Entwurfs Umgebung, um eine benutzerdefinierte Entwurfszeit Umgebung bereitzustellen. Mit dem benutzerdefinierten Designer können Sie eine benutzerdefinierte `MarqueeControl` Implementierung mit animierten Lichtern und blinkenden Text in vielen Kombinationen zusammenstellen. Sie können das assemblierte Steuerelement wie jedes andere Windows Forms Steuerelement in einem Formular verwenden.

Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, sieht Ihr benutzerdefiniertes Steuerelement in etwa wie folgt aus:

![Die APP zeigt ein Marquee an, das Text und eine Schaltfläche zum Starten und Abbrechen anzeigt.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Das komplette Codelisting finden Sie unter Gewusst [wie: Erstellen eines Windows Forms Steuer Elements, das Entwurfszeit Funktionen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))nutzt.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um diese exemplarische Vorgehensweise abzuschließen, benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Im ersten Schritt erstellen Sie das Anwendungsprojekt. Sie verwenden dieses Projekt, um die Anwendung zu erstellen, die das benutzerdefinierte Steuerelement hostet.

Erstellen Sie in Visual Studio ein neues Windows Forms-Anwendungsprojekt, und nennen Sie es **MarqueeControlTest**.

## <a name="create-the-control-library-project"></a>Erstellen des Steuerelement Bibliothek-Projekts

1. Fügen Sie der Projekt Mappe ein Windows Forms-Steuerelement Bibliothek-Projekt hinzu. Nennen Sie das Projekt **MarqueeControlLibrary**.

2. Löschen Sie mithilfe **Projektmappen-Explorer**das Standard Steuerelement des Projekts, indem Sie die Quelldatei mit dem Namen "UserControl1.cs" oder "UserControl1. vb" löschen, je nach ihrer Sprache Ihrer Wahl.

3. Fügen Sie dem Projekt `MarqueeControlLibrary` ein neues <xref:System.Windows.Forms.UserControl> Element hinzu. Benennen Sie die neue Quelldatei mit dem Basisnamen **MarqueeControl**.

4. Erstellen Sie mit **Projektmappen-Explorer**einen neuen Ordner im `MarqueeControlLibrary` Projekt.

5. Klicken Sie mit der rechten Maustaste auf den **Entwurfs** Ordner, und fügen Sie eine neue Klasse hinzu Nennen Sie es **MarqueeControlRootDesigner**.

6. Sie müssen Typen aus der Assembly "System. Design" verwenden. Fügen Sie daher diesen Verweis dem `MarqueeControlLibrary`-Projekt hinzu.

## <a name="reference-the-custom-control-project"></a>Verweisen auf das benutzerdefinierte Steuerelement Projekt

Sie verwenden das `MarqueeControlTest` Projekt, um das benutzerdefinierte Steuerelement zu testen. Das Testprojekt wird das benutzerdefinierte Steuerelement beachten, wenn Sie der `MarqueeControlLibrary` Assembly einen Projekt Verweis hinzufügen.

Fügen Sie im `MarqueeControlTest`-Projekt einen Projekt Verweis auf die `MarqueeControlLibrary`-Assembly hinzu. Stellen Sie sicher, dass Sie die Registerkarte **Projekte** im Dialogfeld **Verweis hinzufügen** verwenden, anstatt direkt auf die `MarqueeControlLibrary` Assembly zu verweisen.

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definieren eines benutzerdefinierten Steuer Elements und seines benutzerdefinierten Designers

Das benutzerdefinierte Steuerelement wird von der <xref:System.Windows.Forms.UserControl>-Klasse abgeleitet. Dies ermöglicht es dem Steuerelement, andere Steuerelemente zu enthalten, und bietet Ihnen eine große Menge an Standardfunktionen.

Das benutzerdefinierte Steuerelement verfügt über einen zugeordneten benutzerdefinierten Designer. Dies ermöglicht es Ihnen, ein eindeutiges Design zu erstellen, das speziell auf das benutzerdefinierte Steuerelement zugeschnitten ist.

Sie ordnen das Steuerelement dem Designer zu, indem Sie die <xref:System.ComponentModel.DesignerAttribute>-Klasse verwenden. Da Sie das gesamte Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements entwickeln, implementiert der benutzerdefinierte Designer die <xref:System.ComponentModel.Design.IRootDesigner>-Schnittstelle.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>So definieren Sie ein benutzerdefiniertes Steuerelement und seinen benutzerdefinierten Designer

1. Öffnen Sie die `MarqueeControl`-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Fügen Sie die <xref:System.ComponentModel.DesignerAttribute> der Deklaration der `MarqueeControl`-Klasse hinzu. Dadurch wird das benutzerdefinierte Steuerelement dem Designer zugeordnet.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Öffnen Sie die `MarqueeControlRootDesigner`-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Ändern Sie die Deklaration von `MarqueeControlRootDesigner`, um von der <xref:System.Windows.Forms.Design.DocumentDesigner>-Klasse zu erben. Wenden Sie den <xref:System.ComponentModel.ToolboxItemFilterAttribute> an, um die Designer Interaktion mit der **Toolbox**anzugeben.

   > [!NOTE]
   > Die Definition für die `MarqueeControlRootDesigner`-Klasse wurde in einen Namespace mit dem Namen "MarqueeControlLibrary. Design" eingeschlossen. Diese Deklaration platziert den Designer in einem speziellen Namespace, der für Entwurfs bezogene Typen reserviert ist.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definieren Sie den Konstruktor für die `MarqueeControlRootDesigner`-Klasse. Fügen Sie im Konstruktortext eine <xref:System.Diagnostics.Trace.WriteLine%2A>-Anweisung ein. Dies ist nützlich für das Debuggen.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Erstellen einer Instanz des benutzerdefinierten Steuer Elements

1. Fügen Sie dem Projekt `MarqueeControlTest` ein neues <xref:System.Windows.Forms.UserControl> Element hinzu. Benennen Sie die neue Quelldatei mit dem Basisnamen " **DemoMarqueeControl**".

2. Öffnen Sie die Datei `DemoMarqueeControl` im **Code-Editor**. Importieren Sie am Anfang der Datei den `MarqueeControlLibrary`-Namespace:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Ändern Sie die Deklaration von `DemoMarqueeControl`, um von der `MarqueeControl`-Klasse zu erben.

4. Erstellen Sie das Projekt.

5. Öffnen Sie Form1 im Windows Forms-Designer.

6. Suchen Sie in der **Toolbox** die Registerkarte " **MarqueeControlTest Components** ", und öffnen Sie Sie. Ziehen Sie eine `DemoMarqueeControl` aus der **Toolbox** auf das Formular.

7. Erstellen Sie das Projekt.

## <a name="set-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts für das Debuggen zur Entwurfszeit

Wenn Sie ein benutzerdefiniertes Entwurfszeit Verhalten entwickeln, müssen Sie die Steuerelemente und Komponenten debuggen. Es gibt eine einfache Möglichkeit zum Einrichten des Projekts, um das Debuggen zur Entwurfszeit zuzulassen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Debuggen von benutzerdefinierten Windows Forms Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Klicken Sie mit der rechten Maustaste auf das Projekt `MarqueeControlLibrary`, und wählen Sie **Eigenschaften**

2. Wählen Sie im Dialogfeld **MarqueeControlLibrary-Eigenschaften Seiten** die Seite **Debuggen** aus.

3. Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten**aus. Sie Debuggen eine separate Instanz von Visual Studio, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)), um nach der Visual Studio-IDE zu suchen. Der Name der ausführbaren Datei lautet "devenv. exe". Wenn Sie am Standard Speicherort installiert haben, lautet der Pfad *% Program Files (x86)% \ Microsoft Visual studio\2019\\\<Edition > \common7\ide\devenv.exe*.

4. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.

5. Klicken Sie mit der rechten Maustaste auf das Projekt MarqueeControlLibrary, und wählen Sie **als Startprojekt festlegen** , um diese Debugkonfiguration zu aktivieren.

## <a name="checkpoint"></a>Checkpoint

Sie können jetzt das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements Debuggen. Nachdem Sie festgestellt haben, dass die Debuggingumgebung ordnungsgemäß eingerichtet wurde, testen Sie die Zuordnung zwischen dem benutzerdefinierten Steuerelement und dem benutzerdefinierten Designer.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>So testen Sie die Debugumgebung und die Designer Zuordnung

1. Öffnen Sie die MarqueeControlRootDesigner-Quelldatei im **Code-Editor** , und platzieren Sie einen Haltepunkt für die <xref:System.Diagnostics.Trace.WriteLine%2A>-Anweisung.

2. Drücken Sie **F5** , um die Debugsitzung zu starten.

   Es wird eine neue Instanz von Visual Studio erstellt.

3. Öffnen Sie in der neuen Instanz von Visual Studio die MarqueeControlTest-Projekt Mappe. Sie können die Lösung problemlos finden, indem Sie im Menü **Datei** die Option **zuletzt verwendete Projekte** auswählen. Die Projektmappendatei "MarqueeControlTest. sln" wird als zuletzt verwendete Datei aufgeführt.

4. Öffnen Sie die `DemoMarqueeControl` im Designer.

   Die debugginginstanz von Visual Studio erhält den Fokus, und die Ausführung wird am Haltepunkt angehalten. Drücken Sie **F5** , um die Debugsitzung fortzusetzen.

An diesem Punkt ist alles vorhanden, um das benutzerdefinierte Steuerelement und den zugehörigen benutzerdefinierten Designer zu entwickeln und zu debuggen. Im restlichen Teil dieses Artikels werden die Details der Implementierung von Features des-Steuer Elements und des-Designers behandelt.

## <a name="implement-the-custom-control"></a>Implementieren des benutzerdefinierten Steuer Elements

Der `MarqueeControl` ist ein <xref:System.Windows.Forms.UserControl> mit etwas Anpassung. Es macht zwei Methoden verfügbar: `Start`, das die Marquee-Animation startet, und `Stop`, das die Animation beendet. Da der `MarqueeControl` untergeordnete Steuerelemente enthält, die die `IMarqueeWidget`-Schnittstelle implementieren, `Start` und `Stop` jedes untergeordnete Steuerelement aufzulisten und die `StartMarquee`-bzw. `StopMarquee` Methoden für jedes untergeordnete Steuerelement aufzurufen, das `IMarqueeWidget`implementiert.

Die Darstellung der Steuerelemente `MarqueeBorder` und `MarqueeText` hängt vom Layout ab, sodass `MarqueeControl` die <xref:System.Windows.Forms.Control.OnLayout%2A>-Methode überschreibt und <xref:System.Windows.Forms.Control.PerformLayout%2A> für untergeordnete Steuerelemente dieses Typs aufruft.

Dies ist der Umfang der `MarqueeControl` Anpassungen. Die Lauf Zeitfunktionen werden durch die Steuerelemente `MarqueeBorder` und `MarqueeText` implementiert, und die Entwurfszeit Funktionen werden durch die Klassen `MarqueeBorderDesigner` und `MarqueeControlRootDesigner` implementiert.

### <a name="to-implement-your-custom-control"></a>So implementieren Sie das benutzerdefinierte Steuerelement

1. Öffnen Sie die `MarqueeControl`-Quelldatei im **Code-Editor**. Implementieren Sie die Methoden `Start` und `Stop`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A> -Methode.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Erstellen eines untergeordneten Steuer Elements für das benutzerdefinierte Steuerelement

Der `MarqueeControl` hostet zwei Arten von untergeordnetem Steuerelement: das `MarqueeBorder`-Steuerelement und das `MarqueeText`-Steuerelement.

- `MarqueeBorder`: dieses Steuerelement zeichnet einen Rahmen von "Lights" um seine Ränder. Die Lichter werden nacheinander blinkt, sodass Sie sich um den Rahmen bewegen. Die Geschwindigkeit, mit der der Speicherstick durch eine Eigenschaft namens "`UpdatePeriod`" gesteuert wird. Verschiedene andere benutzerdefinierte Eigenschaften bestimmen andere Aspekte der Darstellung des Steuer Elements. Zwei Methoden, die als `StartMarquee` und `StopMarquee`bezeichnet werden, Steuern, wann die Animation gestartet und beendet wird.

- `MarqueeText`: dieses Steuerelement zeichnet eine blinkende Zeichenfolge. Wie das `MarqueeBorder`-Steuerelement wird die Geschwindigkeit, mit der der Text blinkt, von der `UpdatePeriod`-Eigenschaft gesteuert. Das `MarqueeText`-Steuerelement verfügt auch über die `StartMarquee`-und `StopMarquee` Methoden, die gemeinsam mit dem `MarqueeBorder` Steuerelement gelten.

Zur Entwurfszeit ermöglicht die `MarqueeControlRootDesigner`, dass diese beiden Steuerelement Typen einer `MarqueeControl` in beliebiger Kombination hinzugefügt werden können.

Allgemeine Funktionen der beiden Steuerelemente werden in eine Schnittstelle mit dem Namen `IMarqueeWidget`einbezogen. Dadurch kann der `MarqueeControl` alle untergeordneten Steuerelemente mit Marquee ermitteln und Ihnen eine besondere Behandlung ermöglichen.

Zum Implementieren des regelmäßigen Animations Features verwenden Sie <xref:System.ComponentModel.BackgroundWorker> Objekte aus dem <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace. Sie können <xref:System.Windows.Forms.Timer> Objekte verwenden. Wenn jedoch viele `IMarqueeWidget` Objekte vorhanden sind, kann der einzige UI-Thread die Animation möglicherweise nicht in der Hand halten.

### <a name="to-create-a-child-control-for-your-custom-control"></a>So erstellen Sie ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement

1. Fügen Sie ein neues Klassen Element zum `MarqueeControlLibrary` Projekt hinzu. Benennen Sie die neue Quelldatei mit dem Basis Namen "IMarqueeWidget".

2. Öffnen Sie die `IMarqueeWidget` Quelldatei im **Code-Editor** , und ändern Sie die Deklaration von `class` in `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Fügen Sie der `IMarqueeWidget`-Schnittstelle den folgenden Code hinzu, um zwei Methoden und eine Eigenschaft zur Bearbeitung der Marquee-Animation verfügbar zu machen:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Fügen Sie dem `MarqueeControlLibrary` Projekt ein neues **benutzerdefiniertes Steuer** Element hinzu. Benennen Sie die neue Quelldatei mit dem Basis Namen "MarqueeText".

5. Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> Komponente aus der **Toolbox** auf das Steuerelement `MarqueeText`. Diese Komponente ermöglicht es dem `MarqueeText` Steuerelement, sich selbst asynchron zu aktualisieren.

6. Legen Sie im Fenster **Eigenschaften** die Eigenschaften `WorkerReportsProgress` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> der <xref:System.ComponentModel.BackgroundWorker> Komponente auf **true**fest. Mit diesen Einstellungen kann die <xref:System.ComponentModel.BackgroundWorker> Komponente das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignis in regelmäßigen Abständen erhöhen und asynchrone Aktualisierungen abbrechen.

   Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

7. Öffnen Sie die `MarqueeText`-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Ändern Sie die Deklaration von `MarqueeText`, um von <xref:System.Windows.Forms.Label> zu erben und die `IMarqueeWidget`-Schnittstelle zu implementieren:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie Sie im Konstruktor. Das `isLit`-Feld bestimmt, ob der Text in der von der `LightColor`-Eigenschaft angegebenen Farbe gezeichnet werden soll.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die Methoden `StartMarquee` und `StopMarquee` rufen die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>-und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden der <xref:System.ComponentModel.BackgroundWorker> Komponente auf, um die Animation zu starten und zu unterbinden.

    Die Attribute "<xref:System.ComponentModel.CategoryAttribute.Category%2A>" und "<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>" werden auf die `UpdatePeriod` Eigenschaft angewendet, sodass Sie in einem benutzerdefinierten Abschnitt der Eigenschaftenfenster mit dem Namen "Marquee" angezeigt wird.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementieren Sie die Eigenschaftenaccessoren. Sie stellen zwei Eigenschaften für Clients bereit: `LightColor` und `DarkColor`. Die Attribute "<xref:System.ComponentModel.CategoryAttribute.Category%2A>" und "<xref:System.ComponentModel.BrowsableAttribute.Browsable%2A>" werden auf diese Eigenschaften angewendet, sodass die Eigenschaften in einem benutzerdefinierten Abschnitt der Eigenschaftenfenster mit dem Namen "Marquee" angezeigt werden.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementieren Sie die Handler für die <xref:System.ComponentModel.BackgroundWorker.DoWork>-und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignisse der <xref:System.ComponentModel.BackgroundWorker> Komponente.

    Der <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler wird für die Anzahl der Millisekunden, die durch angegeben wird `UpdatePeriod` dann das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignis auslöst, bis der Code die Animation durch Aufrufen von <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>beendet.

    Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignishandler schaltet den Text zwischen seinem hellen und dem dunklen Zustand um, um die Darstellung des blinkendes zu gestalten.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode, um die Animation zu aktivieren.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Drücken Sie **F6** , um die Projekt Mappe zu erstellen.

## <a name="create-the-marqueeborder-child-control"></a>Erstellen des untergeordneten MarqueeBorder-Steuer Elements

Das `MarqueeBorder` Steuerelement ist etwas komplexer als das `MarqueeText`-Steuerelement. Sie verfügt über mehr Eigenschaften, und die Animation in der <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode ist eher beteiligt. Im Prinzip ähnelt es dem `MarqueeText`-Steuerelement.

Da das `MarqueeBorder` Steuerelement über untergeordnete Steuerelemente verfügen kann, muss es <xref:System.Windows.Forms.Control.Layout> Ereignisse beachten.

### <a name="to-create-the-marqueeborder-control"></a>So erstellen Sie das MarqueeBorder-Steuerelement

1. Fügen Sie dem `MarqueeControlLibrary` Projekt ein neues **benutzerdefiniertes Steuer** Element hinzu. Benennen Sie die neue Quelldatei mit dem Basis Namen "MarqueeBorder".

2. Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> Komponente aus der **Toolbox** auf das Steuerelement `MarqueeBorder`. Diese Komponente ermöglicht es dem `MarqueeBorder` Steuerelement, sich selbst asynchron zu aktualisieren.

3. Legen Sie im Fenster **Eigenschaften** die Eigenschaften `WorkerReportsProgress` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> der <xref:System.ComponentModel.BackgroundWorker> Komponente auf **true**fest. Mit diesen Einstellungen kann die <xref:System.ComponentModel.BackgroundWorker> Komponente das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignis in regelmäßigen Abständen erhöhen und asynchrone Aktualisierungen abbrechen. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

4. Wählen Sie im Fenster **Eigenschaften** die Schaltfläche **Ereignisse** aus. Fügen Sie Handler für die <xref:System.ComponentModel.BackgroundWorker.DoWork>-und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse an.

5. Öffnen Sie die `MarqueeBorder`-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Ändern Sie die Deklaration von `MarqueeBorder`, um von <xref:System.Windows.Forms.Panel> zu erben und die `IMarqueeWidget`-Schnittstelle zu implementieren.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Deklarieren Sie zwei Enumerationen zum Verwalten des Zustands des `MarqueeBorder`-Steuer Elements: `MarqueeSpinDirection`, das die Richtung bestimmt, in der die Lichter um den Rahmen drehen, und `MarqueeLightShape`, das die Form der Beleuchtung bestimmt (quadratisch oder zirkulär). Platzieren Sie diese Deklarationen vor der Deklaration der `MarqueeBorder`-Klasse.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie Sie im Konstruktor.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die Methoden `StartMarquee` und `StopMarquee` rufen die <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>-und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden der <xref:System.ComponentModel.BackgroundWorker> Komponente auf, um die Animation zu starten und zu unterbinden.

    Da das `MarqueeBorder`-Steuerelement untergeordnete Steuerelemente enthalten kann, listet die `StartMarquee`-Methode alle untergeordneten Steuerelemente auf und ruft `StartMarquee` auf, das `IMarqueeWidget`implementiert. Die `StopMarquee`-Methode verfügt über eine ähnliche Implementierung.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementieren Sie die Eigenschaftenaccessoren. Das `MarqueeBorder`-Steuerelement verfügt über mehrere Eigenschaften zum Steuern des Erscheinungs Bilds.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementieren Sie die Handler für die <xref:System.ComponentModel.BackgroundWorker.DoWork>-und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignisse der <xref:System.ComponentModel.BackgroundWorker> Komponente.

    Der <xref:System.ComponentModel.BackgroundWorker.DoWork>-Ereignishandler wird für die Anzahl der Millisekunden, die durch angegeben wird `UpdatePeriod` dann das <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignis auslöst, bis der Code die Animation durch Aufrufen von <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>beendet.

    Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>-Ereignishandler erhöht die Position des "Basis"-Lichts, von dem der helle/dunkle Zustand der anderen Lichter bestimmt wird, und ruft die <xref:System.Windows.Forms.Control.Refresh%2A>-Methode auf, um zu bewirken, dass sich das Steuerelement selbst neu zeichnet.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementieren Sie die Hilfsmethoden, `IsLit` und `DrawLight`.

    Die `IsLit`-Methode bestimmt die Farbe eines Lichts an einer bestimmten Position. Beleuchtung, die "beleuchtet" sind, werden in der durch die `LightColor`-Eigenschaft angegebenen Farbe gezeichnet, und diejenigen, die "dunkel" sind, werden in der von der `DarkColor`-Eigenschaft angegebenen Farbe gezeichnet.

    Die `DrawLight`-Methode zeichnet mit der entsprechenden Farbe, Form und Position ein Licht.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Überschreiben Sie die Methoden <xref:System.Windows.Forms.Control.OnLayout%2A> und <xref:System.Windows.Forms.Control.OnPaint%2A>.

    Die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode zeichnet die Lichter entlang der Kanten des `MarqueeBorder` Steuer Elements.

    Da die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode von den Dimensionen des `MarqueeBorder` Steuer Elements abhängt, müssen Sie diese immer dann aufzurufen, wenn das Layout geändert wird. Um dies zu erreichen, überschreiben Sie <xref:System.Windows.Forms.Control.OnLayout%2A>, und nennen Sie <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Erstellen eines benutzerdefinierten Designers zum überschatten und Filtern von Eigenschaften

Die `MarqueeControlRootDesigner`-Klasse stellt die-Implementierung für den Stamm Designer bereit. Zusätzlich zu diesem Designer, der auf dem `MarqueeControl`arbeitet, benötigen Sie einen benutzerdefinierten Designer, der speziell mit dem `MarqueeBorder` Steuerelement verknüpft ist. Dieser Designer stellt ein benutzerdefiniertes Verhalten bereit, das im Kontext des benutzerdefinierten root-Designers geeignet ist.

Der `MarqueeBorderDesigner` wird insbesondere bestimmte Eigenschaften des `MarqueeBorder` Steuer Elements "Shadowing" und filtert, sodass die Interaktion mit der Entwurfs Umgebung geändert wird.

Das Abfangen von Aufrufen an den Eigenschafts Accessor einer Komponente wird als "shadodown" bezeichnet. Sie ermöglicht es einem Designer, den vom Benutzer festgelegten Wert zu verfolgen und den Wert optional an die entworfene Komponente zu übergeben.

In diesem Beispiel werden die <xref:System.Windows.Forms.Control.Visible%2A>-und <xref:System.Windows.Forms.Control.Enabled%2A> Eigenschaften durch den `MarqueeBorderDesigner`schattiert, wodurch verhindert wird, dass der Benutzer das `MarqueeBorder` Steuerelement während der Entwurfszeit unsichtbar oder deaktiviert wird.

Designer können auch Eigenschaften hinzufügen und entfernen. In diesem Beispiel wird die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft zur Entwurfszeit entfernt, da das `MarqueeBorder`-Steuerelement die Auffüll Zeichenprogramm gesteuert basierend auf der Größe der Beleuchtung festlegt, die von der `LightSize`-Eigenschaft angegeben wird.

Die Basisklasse für `MarqueeBorderDesigner` ist <xref:System.ComponentModel.Design.ComponentDesigner>. Sie verfügt über Methoden, die die Attribute, Eigenschaften und Ereignisse ändern können, die von einem Steuerelement zur Entwurfszeit verfügbar gemacht werden:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Wenn Sie die öffentliche Schnittstelle einer Komponente mithilfe dieser Methoden ändern, befolgen Sie die folgenden Regeln:

- Nur hinzufügen oder Entfernen von Elementen in den `PreFilter` Methoden

- Ändern vorhandener Elemente nur in den `PostFilter` Methoden

- Die Basis Implementierung sollte immer zuerst in den `PreFilter` Methoden aufgerufen werden.

- Die Basis Implementierung wird immer zuletzt in den `PostFilter`-Methoden aufgerufen.

Durch Einhalten dieser Regeln wird sichergestellt, dass alle Designer in der Entwurfszeit Umgebung über eine konsistente Ansicht aller entworfenen Komponenten verfügen.

Die <xref:System.ComponentModel.Design.ComponentDesigner>-Klasse stellt ein Wörterbuch zum Verwalten der Werte von Shadowing-Eigenschaften bereit, sodass Sie keine bestimmten Instanzvariablen erstellen müssen.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>So erstellen Sie einen benutzerdefinierten Designer zum überschatten und Filtern von Eigenschaften

1. Klicken Sie mit der rechten Maustaste auf den **Entwurfs** Ordner, und fügen Sie eine neue Klasse hinzu Benennen Sie die Quelldatei mit dem Basis Namen " **MarqueeBorderDesigner**".

2. Öffnen Sie die "MarqueeBorderDesigner"-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Ändern Sie die Deklaration von `MarqueeBorderDesigner`, um von <xref:System.Windows.Forms.Design.ParentControlDesigner>zu erben.

    Da das `MarqueeBorder` Steuerelement untergeordnete Steuerelemente enthalten kann, erbt `MarqueeBorderDesigner` von <xref:System.Windows.Forms.Design.ParentControlDesigner>, das die über-/unterordnungshierinteraktion verarbeitet.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Überschreiben Sie die Basis Implementierung von <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementieren Sie die <xref:System.Windows.Forms.Control.Enabled%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft. Diese Implementierungen schattieren die Eigenschaften des Steuer Elements.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Verarbeiten von Komponenten Änderungen

Die `MarqueeControlRootDesigner`-Klasse stellt die benutzerdefinierte Entwurfszeit Darstellung für Ihre `MarqueeControl`-Instanzen bereit. Die meisten Funktionen zur Entwurfszeit werden von der <xref:System.Windows.Forms.Design.DocumentDesigner>-Klasse geerbt. Der Code implementiert zwei spezifische Anpassungen: das Verarbeiten von Komponenten Änderungen und das Hinzufügen von Designer Verben.

Wenn Benutzer ihre `MarqueeControl` Instanzen entwerfen, verfolgt der Stamm-Designer Änderungen an der `MarqueeControl` und den zugehörigen untergeordneten Steuerelementen. Die Entwurfszeit Umgebung bietet einen bequemen Dienst, <xref:System.ComponentModel.Design.IComponentChangeService>, zum Nachverfolgen von Änderungen am Komponenten Status.

Sie erhalten einen Verweis auf diesen Dienst, indem Sie die Umgebung mit der <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A>-Methode Abfragen. Wenn die Abfrage erfolgreich ist, kann der Designer einen Handler für das <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> Ereignis anfügen und alle Aufgaben ausführen, die erforderlich sind, um einen konsistenten Zustand zur Entwurfszeit aufrechtzuerhalten.

Im Fall der `MarqueeControlRootDesigner` Klasse wird die <xref:System.Windows.Forms.Control.Refresh%2A>-Methode für jedes `IMarqueeWidget` Objekt aufgerufen, das in der `MarqueeControl`enthalten ist. Dies bewirkt, dass sich das `IMarqueeWidget` Objekt ordnungsgemäß neu zeichnet, wenn Eigenschaften wie die <xref:System.Windows.Forms.Control.Size%2A> ihres übergeordneten Elements geändert werden.

### <a name="to-handle-component-changes"></a>So verarbeiten Sie Komponenten Änderungen

1. Öffnen Sie die `MarqueeControlRootDesigner`-Quelldatei im **Code-Editor** , und überschreiben Sie die <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>-Methode. Nennen Sie die Basis Implementierung von <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>, und Fragen Sie die <xref:System.ComponentModel.Design.IComponentChangeService>ab.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementieren Sie den <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>-Ereignishandler. Testen Sie den Typ der Sende Komponente, und wenn es sich um einen `IMarqueeWidget`handelt, müssen Sie dessen <xref:System.Windows.Forms.Control.Refresh%2A>-Methode aufzurufen.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Hinzufügen von Designer Verben zum benutzerdefinierten Designer

Ein Designer Verb ist ein Menübefehl, der mit einem Ereignishandler verknüpft ist. Designer Verben werden dem Kontextmenü einer Komponente zur Entwurfszeit hinzugefügt. Weitere Informationen finden Sie unter <xref:System.ComponentModel.Design.DesignerVerb>.

Sie fügen den Designern zwei Designer Verben hinzu: **Test ausführen** und **Test abbrechen**. Diese Verben ermöglichen es Ihnen, das Laufzeitverhalten der `MarqueeControl` zur Entwurfszeit anzuzeigen. Diese Verben werden `MarqueeControlRootDesigner`hinzugefügt.

Wenn **Test ausführen** aufgerufen wird, ruft der Verb-Ereignishandler die `StartMarquee`-Methode für die `MarqueeControl`auf. Wenn **Test beenden** aufgerufen wird, ruft der Verb-Ereignishandler die `StopMarquee`-Methode für die `MarqueeControl`auf. Die Implementierung der `StartMarquee` und `StopMarquee` Methoden ruft diese Methoden für enthaltene Steuerelemente auf, die `IMarqueeWidget`implementieren, sodass alle enthaltenen `IMarqueeWidget` Steuerelemente auch am Test beteiligt sind.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>So fügen Sie Designer Verben zu Ihren benutzerdefinierten Designern hinzu

1. Fügen Sie in der `MarqueeControlRootDesigner`-Klasse Ereignishandler mit dem Namen `OnVerbRunTest` und `OnVerbStopTest`hinzu.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Verbinden Sie diese Ereignishandler mit ihren entsprechenden Designer Verben. `MarqueeControlRootDesigner` erbt eine <xref:System.ComponentModel.Design.DesignerVerbCollection> von seiner Basisklasse. Sie erstellen zwei neue <xref:System.ComponentModel.Design.DesignerVerb> Objekte und fügen diese dieser Sammlung in der <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A>-Methode hinzu.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Erstellen eines benutzerdefinierten uitypeer-Editors

Wenn Sie benutzerdefinierte Entwurfszeit Funktionen für Benutzer erstellen, ist es häufig wünschenswert, eine benutzerdefinierte Interaktion mit dem Eigenschaftenfenster zu erstellen. Dies können Sie erreichen, indem Sie einen <xref:System.Drawing.Design.UITypeEditor>erstellen.

Das `MarqueeBorder`-Steuerelement macht mehrere Eigenschaften im Eigenschaftenfenster verfügbar. Zwei dieser Eigenschaften, `MarqueeSpinDirection` und `MarqueeLightShape` werden durch Enumerationen dargestellt. Um die Verwendung eines UI-typeditors zu veranschaulichen, wird der `MarqueeLightShape`-Eigenschaft <xref:System.Drawing.Design.UITypeEditor>-Klasse zugeordnet.

### <a name="to-create-a-custom-ui-type-editor"></a>So erstellen Sie einen benutzerdefinierten UI-Typ-Editor

1. Öffnen Sie die `MarqueeBorder`-Quelldatei im **Code-Editor**.

2. Deklarieren Sie in der Definition der `MarqueeBorder`-Klasse eine Klasse mit dem Namen `LightShapeEditor`, die von <xref:System.Drawing.Design.UITypeEditor>abgeleitet ist.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable namens `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> -Methode. Diese Implementierung gibt <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>zurück, die der Entwurfs Umgebung mitteilt, wie die `LightShapeEditor`angezeigt werden soll.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> -Methode. Mit dieser Implementierung wird die Entwurfs Umgebung für ein <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Objekt abgefragt. Bei erfolgreicher Ausführung wird eine `LightShapeSelectionControl`erstellt. Die <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A>-Methode wird aufgerufen, um den `LightShapeEditor`zu starten. Der Rückgabewert dieses aufzurufenden wird an die Entwurfs Umgebung zurückgegeben.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Erstellen eines View-Steuer Elements für Ihren benutzerdefinierten uitypeer-Editor

Die `MarqueeLightShape`-Eigenschaft unterstützt zwei Arten von hellen Formen: `Square` und `Circle`. Sie erstellen ein benutzerdefiniertes Steuerelement, das ausschließlich zum Zweck der grafischen Darstellung dieser Werte in der Eigenschaftenfenster verwendet wird. Dieses benutzerdefinierte Steuerelement wird von Ihrem <xref:System.Drawing.Design.UITypeEditor> für die Interaktion mit dem Eigenschaftenfenster verwendet.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>So erstellen Sie ein View-Steuerelement für den benutzerdefinierten Typ-Editor

1. Fügen Sie dem Projekt `MarqueeControlLibrary` ein neues <xref:System.Windows.Forms.UserControl> Element hinzu. Benennen Sie die neue Quelldatei mit dem Basisnamen **LightShapeSelectionControl**.

2. Ziehen Sie zwei <xref:System.Windows.Forms.Panel>-Steuerelemente aus der **Toolbox** auf die `LightShapeSelectionControl`. Benennen Sie Sie `squarePanel` und `circlePanel`. Anordnen Sie diese nebeneinander. Legen Sie die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft beider <xref:System.Windows.Forms.Panel>-Steuerelemente auf **(60, 60)** fest. Legen Sie die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft des `squarePanel`-Steuer Elements auf **(8, 10)** fest. Legen Sie die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft des `circlePanel`-Steuer Elements auf **(80, 10)** fest. Legen Sie abschließend die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft des `LightShapeSelectionControl` auf **(150, 80)** fest.

3. Öffnen Sie die `LightShapeSelectionControl`-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei den <xref:System.Windows.Forms.Design?displayProperty=nameWithType>-Namespace:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implementieren Sie <xref:System.Windows.Forms.Control.Click> Ereignishandler für die `squarePanel`-und `circlePanel`-Steuerelemente. Diese Methoden rufen <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> auf, um die benutzerdefinierte <xref:System.Drawing.Design.UITypeEditor> Bearbeitungs Sitzung zu beenden.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable namens `editorService`.

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Deklarieren Sie eine `MarqueeLightShape` Instanzvariable namens `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. Fügen Sie im `LightShapeSelectionControl`-Konstruktor die <xref:System.Windows.Forms.Control.Click> Ereignishandler an die <xref:System.Windows.Forms.Control.Click> Ereignisse `squarePanel` und `circlePanel` Steuerelemente an. Definieren Sie außerdem eine Konstruktorüberladung, die den `MarqueeLightShape` Wert aus der Entwurfs Umgebung dem Feld `lightShapeValue` zuweist.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. Trennen Sie in der <xref:System.ComponentModel.Component.Dispose%2A>-Methode die <xref:System.Windows.Forms.Control.Click> Ereignishandler.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**. Öffnen Sie die Datei LightShapeSelectionControl.Designer.cs oder LightShapeSelectionControl. Designer. vb, und entfernen Sie die Standard Definition der <xref:System.ComponentModel.Component.Dispose%2A>-Methode.

10. Implementiert die `LightShape`-Eigenschaft.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode. Diese Implementierung zeichnet ein ausgefülltes Quadrat und einen Kreis. Außerdem wird der ausgewählte Wert hervorgehoben, indem ein Rahmen um eine Form gezeichnet wird.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Testen des benutzerdefinierten Steuer Elements im Designer

An diesem Punkt können Sie das `MarqueeControlLibrary` Projekt erstellen. Testen Sie Ihre Implementierung, indem Sie ein Steuerelement erstellen, das von der `MarqueeControl`-Klasse erbt und Sie in einem Formular verwendet.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>So erstellen Sie eine benutzerdefinierte MarqueeControl-Implementierung

1. Öffnen Sie `DemoMarqueeControl` im Windows Forms-Designer. Dadurch wird eine Instanz des `DemoMarqueeControl` Typs erstellt und in einer Instanz des `MarqueeControlRootDesigner` Typs angezeigt.

2. Öffnen Sie in der **Toolbox**die Registerkarte **MarqueeControlLibrary Components** . Die `MarqueeBorder`-und `MarqueeText`-Steuerelemente können angezeigt werden.

3. Ziehen Sie eine Instanz des `MarqueeBorder`-Steuer Elements auf die `DemoMarqueeControl` Entwurfs Oberfläche. Docken Sie dieses `MarqueeBorder` Steuerelement an das übergeordnete Steuerelement.

4. Ziehen Sie eine Instanz des `MarqueeText`-Steuer Elements auf die `DemoMarqueeControl` Entwurfs Oberfläche.

5. Erstellen Sie die Projektmappe.

6. Klicken Sie mit der rechten Maustaste auf die `DemoMarqueeControl`, und wählen Sie im Kontextmenü die Option **Test ausführen** aus, um die Animation zu starten. Klicken Sie auf **Test abbrechen** , um die Animation anzuhalten.

7. Öffnen Sie **Form1** in der Designansicht.

8. Platzieren Sie zwei <xref:System.Windows.Forms.Button>-Steuerelemente auf dem Formular. Benennen Sie Sie `startButton` und `stopButton`, und ändern Sie die Werte der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft in **Start** bzw. **beendet**.

9. Implementieren Sie <xref:System.Windows.Forms.Control.Click> Ereignishandler für die <xref:System.Windows.Forms.Button>-Steuerelemente.

10. Öffnen Sie in der **Toolbox**die Registerkarte **MarqueeControlTest Components** . Sie sehen, dass der `DemoMarqueeControl` zur Auswahl verfügbar ist.

11. Ziehen Sie eine Instanz von `DemoMarqueeControl` auf die Entwurfs Oberfläche **Form1** .

12. Rufen Sie in den <xref:System.Windows.Forms.Control.Click> Ereignis Handlern die Methoden `Start` und `Stop` auf dem `DemoMarqueeControl`auf.

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

13. Legen Sie das `MarqueeControlTest` Projekt als Startprojekt fest, und führen Sie es aus. Das Formular wird angezeigt, in dem Ihre `DemoMarqueeControl`angezeigt wird. Wählen Sie die Schaltfläche **Start** , um die Animation zu starten. Der Text wird blinkt, und die Lichter bewegen sich um den Rahmen.

## <a name="next-steps"></a>Nächste Schritte

Der `MarqueeControlLibrary` veranschaulicht eine einfache Implementierung von benutzerdefinierten Steuerelementen und zugeordneten Designern. Sie können dieses Beispiel auf verschiedene Weise anspruchsvoller gestalten:

- Ändern Sie die Eigenschaftswerte für die `DemoMarqueeControl` im Designer. Fügen Sie weitere `MarqueBorder` Steuerelemente hinzu, und docken Sie diese in ihren übergeordneten Instanzen an, um einen geschachtelten Experimentieren Sie mit unterschiedlichen Einstellungen für den `UpdatePeriod` und die hell bezogenen Eigenschaften.

- Erstellen Sie Ihre eigenen Implementierungen von `IMarqueeWidget`. Sie könnten z. b. ein blindes "Neon Sign" oder ein animiertes Zeichen mit mehreren Bildern erstellen.

- Passen Sie die Entwurfszeit Funktion weiter an. Sie könnten versuchen, mehr Eigenschaften als <xref:System.Windows.Forms.Control.Enabled%2A> und <xref:System.Windows.Forms.Control.Visible%2A>zu shadoauen, und Sie können neue Eigenschaften hinzufügen. Fügen Sie neue Designer Verben hinzu, um häufige Aufgaben wie das Andocken von untergeordneten

- Lizenzieren Sie die `MarqueeControl`.

- Steuern Sie, wie Ihre Steuerelemente serialisiert werden und wie Code für Sie generiert wird. Weitere Informationen finden Sie unter [dynamische Quell Code Generierung und-Kompilierung](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
