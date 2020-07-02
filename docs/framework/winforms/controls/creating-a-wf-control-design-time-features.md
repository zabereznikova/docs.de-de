---
title: Erstellen eines Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt
description: Erfahren Sie, wie Sie einen benutzerdefinierten Designer für ein benutzerdefiniertes Steuerelement in Windows Forms erstellen, das Entwurfszeit Funktionen nutzt.
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
ms.openlocfilehash: 03c04578ecb01b689f58d41a46eef5793fb1182c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613909"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a>Exemplarische Vorgehensweise: Erstellen eines Steuer Elements, das Entwurfszeit Features nutzt

Die Entwurfszeit Darstellung eines benutzerdefinierten Steuer Elements kann durch die Erstellung eines zugeordneten benutzerdefinierten Designers verbessert werden.

Dieser Artikel veranschaulicht das Erstellen eines benutzerdefinierten Designers für ein benutzerdefiniertes Steuerelement. Sie implementieren einen `MarqueeControl` Typ und eine zugehörige Designer Klasse mit dem Namen `MarqueeControlRootDesigner` .

Der `MarqueeControl` Typ implementiert eine Anzeige ähnlich einem Theater-Marquee mit animierten Lichtern und blinkenden Text.

Der Designer für dieses Steuerelement interagiert mit der Entwurfs Umgebung, um eine benutzerdefinierte Entwurfszeit Umgebung bereitzustellen. Mit dem benutzerdefinierten Designer können Sie eine benutzerdefinierte `MarqueeControl` Implementierung mit animierten Lichtern und blinkenden Text in vielen Kombinationen zusammenstellen. Sie können das assemblierte Steuerelement wie jedes andere Windows Forms Steuerelement in einem Formular verwenden.

Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, sieht Ihr benutzerdefiniertes Steuerelement in etwa wie folgt aus:

![Die APP zeigt ein Marquee an, das Text und eine Schaltfläche zum Starten und Abbrechen anzeigt.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Das komplette Codelisting finden Sie unter Gewusst [wie: Erstellen eines Windows Forms Steuer Elements, das Entwurfszeit Funktionen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))nutzt.

## <a name="prerequisites"></a>Voraussetzungen

Um diese exemplarische Vorgehensweise abzuschließen, benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Im ersten Schritt erstellen Sie das Anwendungsprojekt. Sie verwenden dieses Projekt, um die Anwendung zu erstellen, die das benutzerdefinierte Steuerelement hostet.

Erstellen Sie in Visual Studio ein neues Windows Forms-Anwendungsprojekt, und nennen Sie es **MarqueeControlTest**.

## <a name="create-the-control-library-project"></a>Erstellen des Steuerelement Bibliothek-Projekts

1. Fügen Sie der Projekt Mappe ein Windows Forms-Steuerelement Bibliothek-Projekt hinzu. Nennen Sie das Projekt **MarqueeControlLibrary**.

2. Löschen Sie mithilfe **Projektmappen-Explorer**das Standard Steuerelement des Projekts, indem Sie die Quelldatei mit dem Namen "UserControl1.cs" oder "UserControl1. vb" löschen, je nach ihrer Sprache Ihrer Wahl.

3. Fügen Sie <xref:System.Windows.Forms.UserControl> dem Projekt ein neues Element hinzu `MarqueeControlLibrary` . Benennen Sie die neue Quelldatei mit dem Basisnamen **MarqueeControl**.

4. Erstellen Sie mit **Projektmappen-Explorer**einen neuen Ordner im `MarqueeControlLibrary` Projekt.

5. Klicken Sie mit der rechten Maustaste auf den **Entwurfs** Ordner, und fügen Sie eine neue Klasse hinzu Nennen Sie es **MarqueeControlRootDesigner**.

6. Sie müssen Typen aus der Assembly "System. Design" verwenden, um diesen Verweis dem Projekt hinzuzufügen `MarqueeControlLibrary` .

## <a name="reference-the-custom-control-project"></a>Verweisen auf das benutzerdefinierte Steuerelement Projekt

Sie verwenden das `MarqueeControlTest` Projekt, um das benutzerdefinierte Steuerelement zu testen. Das Testprojekt wird das benutzerdefinierte Steuerelement beachten, wenn Sie der Assembly einen Projekt Verweis hinzufügen `MarqueeControlLibrary` .

`MarqueeControlTest`Fügen Sie im-Projekt einen Projekt Verweis auf die `MarqueeControlLibrary` Assembly hinzu. Stellen Sie sicher, dass Sie die Registerkarte **Projekte** im Dialogfeld **Verweis hinzufügen** verwenden, anstatt direkt auf die Assembly zu verweisen `MarqueeControlLibrary` .

## <a name="define-a-custom-control-and-its-custom-designer"></a>Definieren eines benutzerdefinierten Steuer Elements und seines benutzerdefinierten Designers

Das benutzerdefinierte Steuerelement wird von der- <xref:System.Windows.Forms.UserControl> Klasse abgeleitet. Dies ermöglicht es dem Steuerelement, andere Steuerelemente zu enthalten, und bietet Ihnen eine große Menge an Standardfunktionen.

Das benutzerdefinierte Steuerelement verfügt über einen zugeordneten benutzerdefinierten Designer. Dies ermöglicht es Ihnen, ein eindeutiges Design zu erstellen, das speziell auf das benutzerdefinierte Steuerelement zugeschnitten ist.

Das Steuerelement wird mithilfe der-Klasse mit dem Designer verknüpft <xref:System.ComponentModel.DesignerAttribute> . Da Sie das gesamte Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements entwickeln, wird die-Schnittstelle vom benutzerdefinierten Designer implementiert <xref:System.ComponentModel.Design.IRootDesigner> .

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>So definieren Sie ein benutzerdefiniertes Steuerelement und seinen benutzerdefinierten Designer

1. Öffnen Sie die `MarqueeControl` Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Fügen Sie der <xref:System.ComponentModel.DesignerAttribute> `MarqueeControl` Klassen Deklaration hinzu. Dadurch wird das benutzerdefinierte Steuerelement dem Designer zugeordnet.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Öffnen Sie die `MarqueeControlRootDesigner` Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Ändern Sie die Deklaration von `MarqueeControlRootDesigner` , um von der-Klasse zu erben <xref:System.Windows.Forms.Design.DocumentDesigner> . Wenden <xref:System.ComponentModel.ToolboxItemFilterAttribute> Sie das an, um die Designer Interaktion mit der **Toolbox**anzugeben.

   > [!NOTE]
   > Die Definition für die- `MarqueeControlRootDesigner` Klasse wurde in einen Namespace mit dem Namen "MarqueeControlLibrary. Design" eingeschlossen. Diese Deklaration platziert den Designer in einem speziellen Namespace, der für Entwurfs bezogene Typen reserviert ist.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definieren Sie den Konstruktor für die- `MarqueeControlRootDesigner` Klasse. Fügen Sie eine- <xref:System.Diagnostics.Trace.WriteLine%2A> Anweisung in den Konstruktortext ein. Dies ist nützlich für das Debuggen.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a>Erstellen einer Instanz des benutzerdefinierten Steuer Elements

1. Fügen Sie <xref:System.Windows.Forms.UserControl> dem Projekt ein neues Element hinzu `MarqueeControlTest` . Benennen Sie die neue Quelldatei mit dem Basisnamen " **DemoMarqueeControl**".

2. Öffnen Sie die `DemoMarqueeControl` Datei im **Code-Editor**. Importieren Sie am Anfang der Datei den- `MarqueeControlLibrary` Namespace:

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. Ändern Sie die Deklaration von `DemoMarqueeControl` , um von der-Klasse zu erben `MarqueeControl` .

4. Erstellen Sie das Projekt.

5. Öffnen Sie Form1 im Windows Forms-Designer.

6. Suchen Sie in der **Toolbox** die Registerkarte " **MarqueeControlTest Components** ", und öffnen Sie Sie. Ziehen `DemoMarqueeControl` Sie ein aus der **Toolbox** auf das Formular.

7. Erstellen Sie das Projekt.

## <a name="set-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts für das Debuggen zur Entwurfszeit

Wenn Sie ein benutzerdefiniertes Entwurfszeit Verhalten entwickeln, müssen Sie die Steuerelemente und Komponenten debuggen. Es gibt eine einfache Möglichkeit zum Einrichten des Projekts, um das Debuggen zur Entwurfszeit zuzulassen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Debuggen von benutzerdefinierten Windows Forms Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

1. Klicken Sie mit der rechten Maustaste auf das `MarqueeControlLibrary` Projekt und wählen Sie **Eigenschaften**.

2. Wählen Sie im Dialogfeld **MarqueeControlLibrary-Eigenschaften Seiten** die Seite **Debuggen** aus.

3. Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten**aus. Wenn Sie eine separate Instanz von Visual Studio debuggen, klicken Sie auf die ![ Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio ](./media/visual-studio-ellipsis-button.png) ), um nach der Visual Studio-IDE zu suchen. Der Name der ausführbaren Datei ist devenv.exe, und wenn Sie am Standard Speicherort installiert haben, lautet der Pfad *% Program Files (x86)% \ Microsoft Visual studio\2019 \\ \<edition>\Common7\IDE\devenv.exe*.

4. Wählen Sie **OK** aus, um das Dialogfeld zu schließen.

5. Klicken Sie mit der rechten Maustaste auf das Projekt MarqueeControlLibrary, und wählen Sie **als Startprojekt festlegen** , um diese Debugkonfiguration zu aktivieren.

## <a name="checkpoint"></a>Prüfpunkt

Sie können jetzt das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements Debuggen. Nachdem Sie festgestellt haben, dass die Debuggingumgebung ordnungsgemäß eingerichtet wurde, testen Sie die Zuordnung zwischen dem benutzerdefinierten Steuerelement und dem benutzerdefinierten Designer.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>So testen Sie die Debugumgebung und die Designer Zuordnung

1. Öffnen Sie die MarqueeControlRootDesigner-Quelldatei im **Code-Editor** , und platzieren Sie einen Haltepunkt in der- <xref:System.Diagnostics.Trace.WriteLine%2A> Anweisung.

2. Drücken Sie **F5** , um die Debugsitzung zu starten.

   Es wird eine neue Instanz von Visual Studio erstellt.

3. Öffnen Sie in der neuen Instanz von Visual Studio die MarqueeControlTest-Projekt Mappe. Sie können die Lösung problemlos finden, indem Sie im Menü **Datei** die Option **zuletzt verwendete Projekte** auswählen. Die Projektmappendatei "MarqueeControlTest. sln" wird als zuletzt verwendete Datei aufgeführt.

4. Öffnen Sie `DemoMarqueeControl` im Designer.

   Die debugginginstanz von Visual Studio erhält den Fokus, und die Ausführung wird am Haltepunkt angehalten. Drücken Sie **F5** , um die Debugsitzung fortzusetzen.

An diesem Punkt ist alles vorhanden, um das benutzerdefinierte Steuerelement und den zugehörigen benutzerdefinierten Designer zu entwickeln und zu debuggen. Im restlichen Teil dieses Artikels werden die Details der Implementierung von Features des-Steuer Elements und des-Designers behandelt.

## <a name="implement-the-custom-control"></a>Implementieren des benutzerdefinierten Steuer Elements

`MarqueeControl`Ist ein <xref:System.Windows.Forms.UserControl> mit etwas Anpassung. Es macht zwei Methoden verfügbar: `Start` , die die Marquee-Animation startet, und `Stop` , wodurch die Animation beendet wird. Da die untergeordnete `MarqueeControl` Steuerelemente enthält, die die `IMarqueeWidget` -Schnittstelle implementieren, und jedes untergeordnete Steuerelement auflisten `Start` `Stop` und die `StartMarquee` -und-Methoden für jedes untergeordnete Steuerelement aufzählen, `StopMarquee` das implementiert `IMarqueeWidget` .

Die Darstellung des-Steuer Elements und des-Steuer Elements `MarqueeBorder` `MarqueeText` hängt vom Layout ab. Daher wird `MarqueeControl` die-Methode überschrieben <xref:System.Windows.Forms.Control.OnLayout%2A> und für untergeordnete Steuer <xref:System.Windows.Forms.Control.PerformLayout%2A> Elemente dieses Typs aufgerufen.

Dies ist der Umfang der `MarqueeControl` Anpassungen. Die Lauf Zeitfunktionen werden von den `MarqueeBorder` -und-Steuer `MarqueeText` Elementen implementiert, und die Entwurfszeit Funktionen werden von der `MarqueeBorderDesigner` -Klasse und der- `MarqueeControlRootDesigner` Klasse implementiert.

### <a name="to-implement-your-custom-control"></a>So implementieren Sie das benutzerdefinierte Steuerelement

1. Öffnen Sie die `MarqueeControl` Quelldatei im **Code-Editor**. Implementieren Sie `Start` die `Stop` Methoden und.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A> -Methode.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a>Erstellen eines untergeordneten Steuer Elements für das benutzerdefinierte Steuerelement

Der `MarqueeControl` hostet zwei Arten von untergeordnetem Steuerelement: das `MarqueeBorder` -Steuerelement und das- `MarqueeText` Steuerelement.

- `MarqueeBorder`: Dieses Steuerelement zeichnet einen Rahmen von "Lights" um seine Ränder. Die Lichter werden nacheinander blinkt, sodass Sie sich um den Rahmen bewegen. Die Geschwindigkeit, mit der der Lichtblitz durch eine Eigenschaft namens gesteuert wird `UpdatePeriod` . Verschiedene andere benutzerdefinierte Eigenschaften bestimmen andere Aspekte der Darstellung des Steuer Elements. Die zwei Methoden, `StartMarquee` und `StopMarquee` , Steuern, wann die Animation gestartet und beendet wird.

- `MarqueeText`: Dieses Steuerelement zeichnet eine blinkende Zeichenfolge. Wie das- `MarqueeBorder` Steuerelement wird die Geschwindigkeit, mit der der Text blinkt, von der- `UpdatePeriod` Eigenschaft gesteuert. Das `MarqueeText` -Steuerelement verfügt auch über die `StartMarquee` -und-Methoden, die `StopMarquee` mit dem- `MarqueeBorder` Steuerelement

Zur Entwurfszeit `MarqueeControlRootDesigner` können diese beiden Steuerelement Typen `MarqueeControl` in beliebiger Kombination zu hinzugefügt werden.

Allgemeine Funktionen der beiden Steuerelemente werden in eine Schnittstelle mit dem Namen integriert `IMarqueeWidget` . Dies ermöglicht es `MarqueeControl` , alle untergeordneten Steuerelemente mit Marquee zu ermitteln und Ihnen eine besondere Behandlung zu ermöglichen.

Zum Implementieren des regelmäßigen Animations Features verwenden Sie <xref:System.ComponentModel.BackgroundWorker> Objekte aus dem- <xref:System.ComponentModel?displayProperty=nameWithType> Namespace. Sie können <xref:System.Windows.Forms.Timer> Objekte verwenden, aber wenn viele `IMarqueeWidget` Objekte vorhanden sind, kann der einzelne UI-Thread die Animation möglicherweise nicht in der Hand halten.

### <a name="to-create-a-child-control-for-your-custom-control"></a>So erstellen Sie ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement

1. Fügen Sie dem Projekt ein neues Klassen Element hinzu `MarqueeControlLibrary` . Benennen Sie die neue Quelldatei mit dem Basis Namen "IMarqueeWidget".

2. Öffnen `IMarqueeWidget` Sie die Quelldatei im **Code-Editor** , und ändern Sie die Deklaration von in `class` `interface` :

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Fügen Sie der-Schnittstelle den folgenden Code hinzu `IMarqueeWidget` , um zwei Methoden und eine-Eigenschaft zur Bearbeitung der Marquee-Animation verfügbar zu machen:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Fügen Sie dem Projekt ein neues **benutzerdefiniertes Steuer** Element hinzu `MarqueeControlLibrary` . Benennen Sie die neue Quelldatei mit dem Basis Namen "MarqueeText".

5. Ziehen <xref:System.ComponentModel.BackgroundWorker> Sie eine Komponente aus der **Toolbox** auf das `MarqueeText` Steuerelement. Diese Komponente ermöglicht es dem `MarqueeText` Steuerelement, sich selbst asynchron zu aktualisieren.

6. Legen Sie im Fenster **Eigenschaften** die <xref:System.ComponentModel.BackgroundWorker> Eigenschaften und der `WorkerReportsProgress` Komponente <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> auf **true**fest. Diese Einstellungen ermöglichen es der <xref:System.ComponentModel.BackgroundWorker> Komponente, das-Ereignis in regelmäßigen Abständen <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> zu erhöhen und asynchrone Updates abzubrechen.

   Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

7. Öffnen Sie die `MarqueeText` Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Ändern Sie die Deklaration von `MarqueeText` , um von zu erben <xref:System.Windows.Forms.Label> und die- `IMarqueeWidget` Schnittstelle zu implementieren:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie Sie im Konstruktor. Das- `isLit` Feld bestimmt, ob der Text in der Farbe gezeichnet werden soll, die von der-Eigenschaft angegeben wird `LightColor` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die `StartMarquee` - `StopMarquee` Methode und die-Methode rufen die <xref:System.ComponentModel.BackgroundWorker> -und-Methoden der-Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> auf, um die Animation zu starten

    Das <xref:System.ComponentModel.CategoryAttribute.Category%2A> -Attribut und das- <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribut werden auf die-Eigenschaft angewendet, `UpdatePeriod` sodass Sie in einem benutzerdefinierten Abschnitt des Eigenschaftenfenster mit dem Namen "Marquee" angezeigt wird.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementieren Sie die Eigenschaftenaccessoren. Sie stellen zwei Eigenschaften für Clients bereit: `LightColor` und `DarkColor` . Die <xref:System.ComponentModel.CategoryAttribute.Category%2A> <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribute und werden auf diese Eigenschaften angewendet, sodass die Eigenschaften in einem benutzerdefinierten Abschnitt des Eigenschaftenfenster mit dem Namen "Marquee" angezeigt werden.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker> -Ereignis und das-Ereignis der Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Der- <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler wird für die Anzahl von Millisekunden, die durch angegeben wird `UpdatePeriod` , mit dem-Ereignis ausgelöst <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> , bis der Code die Animation durch Aufrufen von beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignishandler schaltet den Text zwischen seinem hellen und dem dunklen Zustand um, um die Darstellung des blinkendes zu gestalten.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Überschreiben <xref:System.Windows.Forms.Control.OnPaint%2A> Sie die-Methode zum Aktivieren der Animation.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Drücken Sie **F6**, um die Projektmappe zu erstellen.

## <a name="create-the-marqueeborder-child-control"></a>Erstellen des untergeordneten MarqueeBorder-Steuer Elements

Das- `MarqueeBorder` Steuerelement ist etwas komplexer als das- `MarqueeText` Steuerelement. Sie verfügt über mehr Eigenschaften, und die Animation in der- <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist eher beteiligt. Im Prinzip ist es dem-Steuerelement sehr ähnlich `MarqueeText` .

Da das Steuerelement über untergeordnete `MarqueeBorder` Steuerelemente verfügen kann, muss es die <xref:System.Windows.Forms.Control.Layout> Ereignisse beachten.

### <a name="to-create-the-marqueeborder-control"></a>So erstellen Sie das MarqueeBorder-Steuerelement

1. Fügen Sie dem Projekt ein neues **benutzerdefiniertes Steuer** Element hinzu `MarqueeControlLibrary` . Benennen Sie die neue Quelldatei mit dem Basis Namen "MarqueeBorder".

2. Ziehen <xref:System.ComponentModel.BackgroundWorker> Sie eine Komponente aus der **Toolbox** auf das `MarqueeBorder` Steuerelement. Diese Komponente ermöglicht es dem `MarqueeBorder` Steuerelement, sich selbst asynchron zu aktualisieren.

3. Legen Sie im Fenster **Eigenschaften** die <xref:System.ComponentModel.BackgroundWorker> Eigenschaften und der `WorkerReportsProgress` Komponente <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> auf **true**fest. Diese Einstellungen ermöglichen es der <xref:System.ComponentModel.BackgroundWorker> Komponente, das-Ereignis in regelmäßigen Abständen <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> zu erhöhen und asynchrone Updates abzubrechen. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

4. Wählen Sie im Fenster **Eigenschaften** die Schaltfläche **Ereignisse** aus. Anfügen von Handlern für die <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse und.

5. Öffnen Sie die `MarqueeBorder` Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Ändern Sie die Deklaration von `MarqueeBorder` , um von zu erben <xref:System.Windows.Forms.Panel> und die- `IMarqueeWidget` Schnittstelle zu implementieren.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Deklarieren Sie zwei Enumerationen zum Verwalten des `MarqueeBorder` Zustands des Steuer Elements: `MarqueeSpinDirection` , das die Richtung bestimmt, in der die Lichter um den Rahmen drehen, und `MarqueeLightShape` , das die Form der Beleuchtung bestimmt (quadratisch oder zirkulär). Platzieren Sie diese Deklarationen vor der `MarqueeBorder` Klassen Deklaration.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren Sie Sie im Konstruktor.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die `StartMarquee` - `StopMarquee` Methode und die-Methode rufen die <xref:System.ComponentModel.BackgroundWorker> -und-Methoden der-Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> auf, um die Animation zu starten

    Da das Steuerelement untergeordnete `MarqueeBorder` Steuerelemente enthalten kann, `StartMarquee` Listet die-Methode alle untergeordneten Steuerelemente auf und ruft die auf, die `StartMarquee` implementieren `IMarqueeWidget` . Die- `StopMarquee` Methode verfügt über eine ähnliche Implementierung.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementieren Sie die Eigenschaftenaccessoren. Das- `MarqueeBorder` Steuerelement verfügt über mehrere Eigenschaften zum Steuern des Erscheinungs Bilds.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementieren Sie die Handler für das <xref:System.ComponentModel.BackgroundWorker> -Ereignis und das-Ereignis der Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> .

    Der- <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler wird für die Anzahl von Millisekunden, die durch angegeben wird `UpdatePeriod` , mit dem-Ereignis ausgelöst <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> , bis der Code die Animation durch Aufrufen von beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> .

    Der <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignishandler erhöht die Position des "Basis"-Lichts, von dem der helle/dunkle Zustand der anderen Lichter bestimmt wird, und ruft die- <xref:System.Windows.Forms.Control.Refresh%2A> Methode auf, um das Steuerelement neu zu zeichnen.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementieren Sie die Hilfsmethoden `IsLit` und `DrawLight` .

    Die- `IsLit` Methode bestimmt die Farbe eines Lichts an einer bestimmten Position. Beleuchtung, die "beleuchtet" sind, werden in der durch die-Eigenschaft angegebenen Farbe gezeichnet `LightColor` , und diejenigen, die "dunkel" sind, werden in der durch die-Eigenschaft angegebenen Farbe gezeichnet `DarkColor` .

    Die- `DrawLight` Methode zeichnet ein Licht mit der entsprechenden Farbe, Form und Position.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A>- und <xref:System.Windows.Forms.Control.OnPaint%2A>-Methoden.

    Die- <xref:System.Windows.Forms.Control.OnPaint%2A> Methode zeichnet die Lichter entlang der Ränder des- `MarqueeBorder` Steuer Elements.

    Da die- <xref:System.Windows.Forms.Control.OnPaint%2A> Methode von den Abmessungen des Steuer Elements abhängt `MarqueeBorder` , müssen Sie diese immer dann aufzurufen, wenn das Layout geändert wird. Überschreiben Sie hierzu, <xref:System.Windows.Forms.Control.OnLayout%2A> und wenden Sie an <xref:System.Windows.Forms.Control.Refresh%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a>Erstellen eines benutzerdefinierten Designers zum überschatten und Filtern von Eigenschaften

Die- `MarqueeControlRootDesigner` Klasse stellt die-Implementierung für den Stamm Designer bereit. Zusätzlich zu diesem Designer, der auf dem arbeitet `MarqueeControl` , benötigen Sie einen benutzerdefinierten Designer, der speziell dem-Steuerelement zugeordnet ist `MarqueeBorder` . Dieser Designer stellt ein benutzerdefiniertes Verhalten bereit, das im Kontext des benutzerdefinierten root-Designers geeignet ist.

Insbesondere `MarqueeBorderDesigner` werden bestimmte Eigenschaften im Steuerelement durch den "Schatten" und gefiltert, sodass die `MarqueeBorder` Interaktion mit der Entwurfs Umgebung geändert wird.

Das Abfangen von Aufrufen an den Eigenschafts Accessor einer Komponente wird als "shadodown" bezeichnet. Sie ermöglicht es einem Designer, den vom Benutzer festgelegten Wert zu verfolgen und den Wert optional an die entworfene Komponente zu übergeben.

In diesem Beispiel werden die <xref:System.Windows.Forms.Control.Visible%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.Forms.Control.Enabled%2A> durch das schattiert `MarqueeBorderDesigner` , wodurch verhindert wird, dass das `MarqueeBorder` Steuerelement während der Entwurfszeit unsichtbar oder deaktiviert wird.

Designer können auch Eigenschaften hinzufügen und entfernen. In diesem Beispiel wird die- <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft zur Entwurfszeit entfernt, da das- `MarqueeBorder` Steuerelement den Abstand basierend auf der Größe der von der-Eigenschaft angegebenen Beleuchtung Programm gesteuert festlegt `LightSize` .

Die Basisklasse für `MarqueeBorderDesigner` ist <xref:System.ComponentModel.Design.ComponentDesigner> , die über Methoden verfügt, die die Attribute, Eigenschaften und Ereignisse ändern können, die von einem Steuerelement zur Entwurfszeit verfügbar gemacht werden:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Wenn Sie die öffentliche Schnittstelle einer Komponente mithilfe dieser Methoden ändern, befolgen Sie die folgenden Regeln:

- Nur Elemente in den Methoden hinzufügen oder entfernen `PreFilter`

- Nur vorhandene Elemente in den `PostFilter` Methoden ändern

- Die Basis Implementierung sollte immer zuerst in den Methoden aufgerufen werden. `PreFilter`

- Die Basis Implementierung sollte immer zuletzt in den Methoden aufgerufen werden. `PostFilter`

Durch Einhalten dieser Regeln wird sichergestellt, dass alle Designer in der Entwurfszeit Umgebung über eine konsistente Ansicht aller entworfenen Komponenten verfügen.

Die- <xref:System.ComponentModel.Design.ComponentDesigner> Klasse stellt ein Wörterbuch zum Verwalten der Werte von Shadowing-Eigenschaften bereit, sodass Sie keine bestimmten Instanzvariablen erstellen müssen.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>So erstellen Sie einen benutzerdefinierten Designer zum überschatten und Filtern von Eigenschaften

1. Klicken Sie mit der rechten Maustaste auf den **Entwurfs** Ordner, und fügen Sie eine neue Klasse hinzu Benennen Sie die Quelldatei mit dem Basis Namen " **MarqueeBorderDesigner**".

2. Öffnen Sie die "MarqueeBorderDesigner"-Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Ändern Sie die Deklaration von `MarqueeBorderDesigner` , um von zu erben <xref:System.Windows.Forms.Design.ParentControlDesigner> .

    Da das `MarqueeBorder` Steuerelement untergeordnete Steuerelemente enthalten kann, `MarqueeBorderDesigner` erbt von <xref:System.Windows.Forms.Design.ParentControlDesigner> , wodurch die über-/unterordnungsinteraktion verarbeitet wird.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Überschreiben Sie die Basis Implementierung von <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementieren Sie die <xref:System.Windows.Forms.Control.Enabled%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft. Diese Implementierungen schattieren die Eigenschaften des Steuer Elements.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a>Verarbeiten von Komponenten Änderungen

Die- `MarqueeControlRootDesigner` Klasse stellt die benutzerdefinierte Entwurfszeit Darstellung für Ihre- `MarqueeControl` Instanzen bereit. Die meisten Entwurfszeit Funktionen werden von der-Klasse geerbt <xref:System.Windows.Forms.Design.DocumentDesigner> . Der Code implementiert zwei spezifische Anpassungen: das Verarbeiten von Komponenten Änderungen und das Hinzufügen von Designer Verben.

Wenn Benutzer ihre `MarqueeControl` Instanzen entwerfen, verfolgt der Stamm-Designer Änderungen an und den untergeordneten Steuer `MarqueeControl` Elementen. Die Entwurfszeit Umgebung bietet einen bequemen Dienst, <xref:System.ComponentModel.Design.IComponentChangeService> , zum Nachverfolgen von Änderungen am Komponenten Status.

Sie erhalten einen Verweis auf diesen Dienst, indem Sie die-Umgebung mit der- <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> Methode Abfragen. Wenn die Abfrage erfolgreich ist, kann der Designer einen Handler für das <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> Ereignis anfügen und alle Aufgaben ausführen, die erforderlich sind, um einen konsistenten Zustand zur Entwurfszeit aufrechtzuerhalten.

Im Fall der- `MarqueeControlRootDesigner` Klasse wird die- <xref:System.Windows.Forms.Control.Refresh%2A> Methode für jedes Objekt aufgerufen, `IMarqueeWidget` das in enthalten ist `MarqueeControl` . Dadurch wird das `IMarqueeWidget` Objekt selbst ordnungsgemäß neu gezeichnet, wenn Eigenschaften wie die der übergeordneten Elemente <xref:System.Windows.Forms.Control.Size%2A> geändert werden.

### <a name="to-handle-component-changes"></a>So verarbeiten Sie Komponenten Änderungen

1. Öffnen Sie die `MarqueeControlRootDesigner` Quelldatei im **Code-Editor** , und überschreiben Sie die- <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode. Nennen Sie die Basis Implementierung von, <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> und Fragen Sie den ab <xref:System.ComponentModel.Design.IComponentChangeService> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementieren Sie den- <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> Ereignishandler. Testen Sie den Typ der sendenden Komponente, und wenn es sich um eine handelt, müssen Sie die zugehörige- `IMarqueeWidget` <xref:System.Windows.Forms.Control.Refresh%2A> Methode

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a>Hinzufügen von Designer Verben zum benutzerdefinierten Designer

Ein Designerverb ist ein mit einem Ereignishandler verknüpfter Menübefehl. Designer Verben werden dem Kontextmenü einer Komponente zur Entwurfszeit hinzugefügt. Weitere Informationen finden Sie unter <xref:System.ComponentModel.Design.DesignerVerb>.

Sie fügen den Designern zwei Designer Verben hinzu: **Test ausführen** und **Test abbrechen**. Diese Verben ermöglichen es Ihnen, das Laufzeitverhalten von zur `MarqueeControl` Entwurfszeit anzuzeigen. Diese Verben werden hinzugefügt `MarqueeControlRootDesigner` .

Wenn **Run Test** aufgerufen wird, ruft der Verb-Ereignishandler die- `StartMarquee` Methode für den auf `MarqueeControl` . Wenn **Test beenden** aufgerufen wird, ruft der Verb-Ereignishandler die- `StopMarquee` Methode für den auf `MarqueeControl` . Die Implementierung der `StartMarquee` -Methode und der- `StopMarquee` Methode ruft diese Methoden für enthaltene Steuerelemente auf, die implementieren `IMarqueeWidget` , sodass alle darin enthaltenen Steuer `IMarqueeWidget` Elemente auch an dem Test teilnehmen.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>So fügen Sie Designer Verben zu Ihren benutzerdefinierten Designern hinzu

1. `MarqueeControlRootDesigner`Fügen Sie in der-Klasse Ereignishandler mit dem Namen `OnVerbRunTest` und hinzu `OnVerbStopTest` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Verbinden Sie diese Ereignishandler mit ihren entsprechenden Designer Verben. `MarqueeControlRootDesigner`erbt eine <xref:System.ComponentModel.Design.DesignerVerbCollection> von ihrer Basisklasse. Sie erstellen zwei neue <xref:System.ComponentModel.Design.DesignerVerb> -Objekte und fügen diese dieser Auflistung in der- <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode hinzu.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a>Erstellen eines benutzerdefinierten uitypeer-Editors

Wenn Sie benutzerdefinierte Entwurfszeit Funktionen für Benutzer erstellen, ist es häufig wünschenswert, eine benutzerdefinierte Interaktion mit dem Eigenschaftenfenster zu erstellen. Dies können Sie erreichen, indem Sie einen erstellen <xref:System.Drawing.Design.UITypeEditor> .

Das-Steuerelement macht `MarqueeBorder` mehrere Eigenschaften im Eigenschaftenfenster verfügbar. Zwei dieser Eigenschaften `MarqueeSpinDirection` und `MarqueeLightShape` werden durch Enumerationen dargestellt. Um die Verwendung eines UI-typeditors zu veranschaulichen, wird der-Eigenschaft eine zugeordnete- `MarqueeLightShape` <xref:System.Drawing.Design.UITypeEditor> Klasse zugeordnet.

### <a name="to-create-a-custom-ui-type-editor"></a>So erstellen Sie einen benutzerdefinierten UI-Typ-Editor

1. Öffnen Sie die `MarqueeBorder` Quelldatei im **Code-Editor**.

2. Deklarieren Sie in der Definition der- `MarqueeBorder` Klasse eine Klasse mit dem Namen `LightShapeEditor` , die von abgeleitet wird <xref:System.Drawing.Design.UITypeEditor> .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable namens `editorService` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> -Methode. Diese Implementierung gibt zurück <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> , die der Entwurfs Umgebung mitteilt, wie das angezeigt werden soll `LightShapeEditor` .

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> -Methode. Mit dieser Implementierung wird die Entwurfs Umgebung für ein Objekt abgefragt <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> . Bei erfolgreicher Ausführung wird ein erstellt `LightShapeSelectionControl` . Die- <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> Methode wird aufgerufen, um das zu starten `LightShapeEditor` . Der Rückgabewert dieses aufzurufenden wird an die Entwurfs Umgebung zurückgegeben.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a>Erstellen eines View-Steuer Elements für Ihren benutzerdefinierten uitypeer-Editor

Die `MarqueeLightShape` -Eigenschaft unterstützt zwei Arten von hellen Formen: `Square` und `Circle` . Sie erstellen ein benutzerdefiniertes Steuerelement, das ausschließlich zum Zweck der grafischen Darstellung dieser Werte in der Eigenschaftenfenster verwendet wird. Dieses benutzerdefinierte Steuerelement wird von Ihrem <xref:System.Drawing.Design.UITypeEditor> für die Interaktion mit dem Eigenschaftenfenster verwendet.

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>So erstellen Sie ein View-Steuerelement für den benutzerdefinierten Typ-Editor

1. Fügen Sie <xref:System.Windows.Forms.UserControl> dem Projekt ein neues Element hinzu `MarqueeControlLibrary` . Benennen Sie die neue Quelldatei mit dem Basisnamen **LightShapeSelectionControl**.

2. Ziehen Sie zwei-Steuer <xref:System.Windows.Forms.Panel> Elemente aus der **Toolbox** auf das `LightShapeSelectionControl` . Benennen Sie Sie `squarePanel` und `circlePanel` . Anordnen Sie diese nebeneinander. Legen Sie die-Eigenschaft beider Steuer <xref:System.Windows.Forms.Control.Size%2A> <xref:System.Windows.Forms.Panel> Elemente auf **(60, 60)** fest. Legen Sie die- <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des- `squarePanel` Steuer Elements auf **(8, 10)** fest. Legen Sie die- <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des- `circlePanel` Steuer Elements auf **(80, 10)** fest. Legen Sie abschließend die- <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft von `LightShapeSelectionControl` auf **(150, 80)** fest.

3. Öffnen Sie die `LightShapeSelectionControl` Quelldatei im **Code-Editor**. Importieren Sie am Anfang der Datei den- <xref:System.Windows.Forms.Design?displayProperty=nameWithType> Namespace:

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. Implementieren Sie <xref:System.Windows.Forms.Control.Click> Ereignishandler für die `squarePanel` Steuer `circlePanel` Elemente und. Diese Methoden rufen <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> auf, um die benutzerdefinierte <xref:System.Drawing.Design.UITypeEditor> Bearbeitungs Sitzung zu beenden.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable namens `editorService` .

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. Deklarieren Sie eine `MarqueeLightShape` Instanzvariable namens `lightShapeValue` .

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. `LightShapeSelectionControl`Fügen Sie im Konstruktor die <xref:System.Windows.Forms.Control.Click> Ereignishandler an die `squarePanel` Ereignisse und der Steuerelemente an `circlePanel` <xref:System.Windows.Forms.Control.Click> . Definieren Sie außerdem eine Konstruktorüberladung, die den `MarqueeLightShape` Wert aus der Entwurfs Umgebung dem `lightShapeValue` Feld zuweist.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. Trennen Sie in der- <xref:System.ComponentModel.Component.Dispose%2A> Methode die <xref:System.Windows.Forms.Control.Click> Ereignishandler.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**. Öffnen Sie die Datei LightShapeSelectionControl.Designer.cs oder LightShapeSelectionControl. Designer. vb, und entfernen Sie die Standard Definition der <xref:System.ComponentModel.Component.Dispose%2A> Methode.

10. Implementiert die `LightShape`-Eigenschaft.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode. Diese Implementierung zeichnet ein ausgefülltes Quadrat und einen Kreis. Außerdem wird der ausgewählte Wert hervorgehoben, indem ein Rahmen um eine Form gezeichnet wird.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a>Testen des benutzerdefinierten Steuer Elements im Designer

An diesem Punkt können Sie das Projekt erstellen `MarqueeControlLibrary` . Testen Sie Ihre Implementierung, indem Sie ein Steuerelement erstellen, das von der `MarqueeControl` -Klasse erbt und es in einem Formular verwendet.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>So erstellen Sie eine benutzerdefinierte MarqueeControl-Implementierung

1. Öffnen Sie `DemoMarqueeControl` im Windows Forms-Designer. Dadurch wird eine Instanz des `DemoMarqueeControl` Typs erstellt und in einer Instanz des `MarqueeControlRootDesigner` Typs angezeigt.

2. Öffnen Sie in der **Toolbox**die Registerkarte **MarqueeControlLibrary Components** . Sie sehen, dass die Steuer `MarqueeBorder` `MarqueeText` Elemente und verfügbar sind.

3. Ziehen Sie eine Instanz des `MarqueeBorder` Steuer Elements auf die `DemoMarqueeControl` Entwurfs Oberfläche. Docken `MarqueeBorder` Sie dieses Steuerelement an das übergeordnete Steuerelement

4. Ziehen Sie eine Instanz des `MarqueeText` Steuer Elements auf die `DemoMarqueeControl` Entwurfs Oberfläche.

5. Erstellen Sie die Projektmappe.

6. Klicken Sie mit der rechten Maustaste auf das `DemoMarqueeControl` , und wählen Sie im Kontextmenü die Option **Test ausführen** aus, um die Animation zu starten. Klicken Sie auf **Test abbrechen** , um die Animation anzuhalten.

7. Öffnen Sie **Form1** in Designansicht.

8. Platzieren Sie zwei-Steuer <xref:System.Windows.Forms.Button> Elemente auf dem Formular. Benennen Sie Sie `startButton` und `stopButton` , und ändern Sie die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaftswerte zum **starten** bzw. zum **Ende**.

9. Implementieren Sie <xref:System.Windows.Forms.Control.Click> Ereignishandler für beide Steuer <xref:System.Windows.Forms.Button> Elemente.

10. Öffnen Sie in der **Toolbox**die Registerkarte **MarqueeControlTest Components** . Sie sehen, `DemoMarqueeControl` dass die Auswahl verfügbar ist.

11. Ziehen Sie eine Instanz von `DemoMarqueeControl` auf die **Form1** -Entwurfs Oberfläche.

12. Rufen Sie in den <xref:System.Windows.Forms.Control.Click> -Ereignis Handlern die `Start` -Methode und die- `Stop` Methode für auf `DemoMarqueeControl` .

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

13. Legen `MarqueeControlTest` Sie das Projekt als Startprojekt fest, und führen Sie es aus. Das Formular wird angezeigt `DemoMarqueeControl` . Wählen Sie die Schaltfläche **Start** , um die Animation zu starten. Der Text wird blinkt, und die Lichter bewegen sich um den Rahmen.

## <a name="next-steps"></a>Nächste Schritte

Der `MarqueeControlLibrary` veranschaulicht eine einfache Implementierung von benutzerdefinierten Steuerelementen und zugeordneten Designern. Sie können dieses Beispiel auf verschiedene Weise anspruchsvoller gestalten:

- Ändern Sie die Eigenschaftswerte für `DemoMarqueeControl` im Designer. Fügen Sie weitere Steuer `MarqueBorder` Elemente hinzu, und docken Sie Sie in ihren übergeordneten Instanzen an, um einen geschachtelten Experimentieren Sie mit verschiedenen Einstellungen für `UpdatePeriod` und den hell bezogenen Eigenschaften.

- Erstellen Sie Ihre eigenen Implementierungen von `IMarqueeWidget` . Sie könnten z. b. ein blindes "Neon Sign" oder ein animiertes Zeichen mit mehreren Bildern erstellen.

- Passen Sie die Entwurfszeit Funktion weiter an. Sie könnten versuchen, mehr Eigenschaften als und zu shadoauen <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Visible%2A> , und Sie können neue Eigenschaften hinzufügen. Fügen Sie neue Designer Verben hinzu, um häufige Aufgaben wie das Andocken von untergeordneten

- Lizenzieren Sie den `MarqueeControl` .

- Steuern Sie, wie Ihre Steuerelemente serialisiert werden und wie Code für Sie generiert wird. Weitere Informationen finden Sie unter [dynamische Quell Code Generierung und-Kompilierung](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
