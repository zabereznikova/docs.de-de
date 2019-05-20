---
title: 'Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktionen nutzt'
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
ms.openlocfilehash: 4d741beffa5649d1d1593ba3dbb7a1918b669b80
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882316"
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a>Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktionen nutzt

Die zur Entwurfszeit für ein benutzerdefiniertes Steuerelement kann verbessert werden, indem Sie einen zugeordneten benutzerdefinierten Designer erstellen.

Diese exemplarische Vorgehensweise veranschaulicht, wie Sie einen benutzerdefinierten Designer für ein benutzerdefiniertes Steuerelement zu erstellen. Implementieren Sie eine `MarqueeControl` Typ und einen zugeordneten Designer Klasse namens `MarqueeControlRootDesigner`.

Die `MarqueeControl` Typ implementiert eine Anzeige ähnlich wie eine Laufschrift Theater mit animierten Lichtern und blinkenden Text.

Der Designer für dieses Steuerelement interagiert mit der entwurfsumgebung, um eine benutzerdefinierte während der Entwurfszeit-Erlebnis zu bieten. Mit dem benutzerdefinierten Designer können Sie eine benutzerdefinierte zusammenstellen `MarqueeControl` -Implementierung mit animierten Lichtern und blinkenden Text in verschiedenen Kombinationen. Sie können das erstellte Steuerelement in einem Formular wie jedes andere Windows Forms-Steuerelement verwenden.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts

- Erstellen ein Steuerelementbibliothek-Projekt

- Verweisen auf das Projekt des benutzerdefinierten Steuerelements

- Definieren ein benutzerdefiniertes Steuerelement und seinen benutzerdefinierte Designer

- Erstellen einer Instanz des benutzerdefinierten Steuerelements

- Einrichten des Projekts für das Debuggen zur Entwurfszeit

- Implementieren des benutzerdefinierten Steuerelements

- Erstellen ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement

- Erstellen des untergeordneten MarqueeBorder-Steuerelements

- Erstellen eines benutzerdefinierten Designers Schatten und Filtereigenschaften

- Behandeln Änderungen an der Clientkomponenten

- Hinzufügen von Designerverben zu Ihrem benutzerdefinierten Designer

- Erstellen eine benutzerdefinierte UITypeEditor

- Testen das benutzerdefinierte Steuerelement im Designer

Wenn Sie fertig sind, wird das benutzerdefinierte Steuerelement etwa wie folgt aussehen:

![Die app einen Auswahlbereich sagen, Text und ein Start- und Stop-Schaltflächen angezeigt.](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

Die vollständige codeauflistung finden Sie unter [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeitfeatures nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).

> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="prerequisites"></a>Vorraussetzungen

Um diese exemplarische Vorgehensweise abzuschließen, benötigen Sie Visual Studio.

## <a name="creating-the-project"></a>Erstellen des Projekts

Der erste Schritt ist das Anwendungsprojekt zu erstellen. Sie können dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.

Öffnen Sie Visual Studio, und erstellen Sie eine Windows Forms-Anwendung mit dem Namen "MarqueeControlTest" (**Datei** > **neu** > **Projekt**  >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).

## <a name="creating-a-control-library-project"></a>Erstellen ein Steuerelementbibliothek-Projekt

Der nächste Schritt besteht darin die Steuerelementbibliothek-Projekt zu erstellen. Erstellen Sie ein neues benutzerdefiniertes Steuerelement und den entsprechenden benutzerdefinierten Designer.

### <a name="to-create-the-control-library-project"></a>Um die Steuerelementbibliothek-Projekt zu erstellen.

1. Fügen Sie ein Windows Forms-Steuerelementbibliothek-Projekt zur Projektmappe hinzu. Nennen Sie das Projekt "MarqueeControlLibrary."

2. Mithilfe von **Projektmappen-Explorer**, löschen Sie Standardsteuerelement des Projekts, indem Sie die Quelldatei, die mit dem Namen "UserControl1.cs" oder "UserControl1.vb", abhängig von der Sprache Ihrer Wahl löschen. Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).

3. Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die `MarqueeControlLibrary` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "MarqueeControl."

4. Mithilfe von **Projektmappen-Explorer**, erstellen Sie einen neuen Ordner in der `MarqueeControlLibrary` Projekt. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)). Nennen Sie den neuen Ordner "Entwurf".

5. Mit der rechten Maustaste die **Entwurf** Ordner, und fügen Sie eine neue Klasse hinzu. Benennen Sie der Quelldatei Basis von "MarqueeControlRootDesigner."

6. Sie benötigen zum Verwenden von Typen aus der Assembly "System.Design" so fügen Sie dieser Verweis auf die `MarqueeControlLibrary` Projekt.

    > [!NOTE]
    > Um die Assembly "System.Design" verwenden zu können, muss Ihr Projekt als Ziel die Vollversion von .NET Framework, nicht die .NET Framework Client Profile. Wenn das Zielframework ändern möchten, finden Sie unter [Vorgehensweise: Erstellen von Projekten für eine bestimmte .NET Framework-Version](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

## <a name="referencing-the-custom-control-project"></a>Verweisen auf das Projekt des benutzerdefinierten Steuerelements

Verwenden Sie die `MarqueeControlTest` Projekt zum Testen des benutzerdefinierten Steuerelements. Das Testprojekt werden über das benutzerdefinierte Steuerelement, wenn Sie einen Projektverweis zum Hinzufügen der `MarqueeControlLibrary` Assembly.

### <a name="to-reference-the-custom-control-project"></a>Um auf das benutzerdefinierte Steuerelement-Projekt zu verweisen.

- In der `MarqueeControlTest` fügen einen Projektverweis auf die `MarqueeControlLibrary` Assembly. Verwenden Sie die **Projekte** Registerkarte die **Verweis hinzufügen** Dialogfeld anstelle von Verweisen auf die `MarqueeControlLibrary` Assembly direkt.

## <a name="defining-a-custom-control-and-its-custom-designer"></a>Definieren ein benutzerdefiniertes Steuerelement und seinen benutzerdefinierte Designer
 Das benutzerdefinierte Steuerelement abgeleitet wird die <xref:System.Windows.Forms.UserControl> Klasse. Dadurch wird das Steuerelement andere Steuerelemente enthalten, und sie erhalten dem Steuerelement auf einen Großteil der Standardfunktionen.

 Das benutzerdefinierte Steuerelement müssen einen zugeordneten Designer. Dadurch können Sie einen eindeutigen Eindruck maßgeschneidert für Ihr benutzerdefiniertes Steuerelement zu erstellen.

 Sie ordnen das Steuerelement den Designer mit der <xref:System.ComponentModel.DesignerAttribute> Klasse. Da Sie das gesamte Design-Time-Verhalten des benutzerdefinierten Steuerelements entwickeln, implementiert der benutzerdefinierte Designer die <xref:System.ComponentModel.Design.IRootDesigner> Schnittstelle.

### <a name="to-define-a-custom-control-and-its-custom-designer"></a>Zum Definieren eines benutzerdefinierten Steuerelements und der benutzerdefinierten designer

1. Öffnen der `MarqueeControl` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces ein:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. Hinzufügen der <xref:System.ComponentModel.DesignerAttribute> auf die `MarqueeControl` Klassendeklaration. Dadurch wird das benutzerdefinierte Steuerelement mit ihren Designer verknüpft.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. Öffnen der `MarqueeControlRootDesigner` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces ein:

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. Ändern Sie die Deklaration der `MarqueeControlRootDesigner` das erben die <xref:System.Windows.Forms.Design.DocumentDesigner> Klasse. Anwenden der <xref:System.ComponentModel.ToolboxItemFilterAttribute> an die Designer-Interaktion mit der **Toolbox**.

     **Beachten Sie** die Definition für die `MarqueeControlRootDesigner` Klasse verfügt über eingeschlossen wurde, in einem Namespace namens "MarqueeControlLibrary.Design." Diese Deklaration setzt der Designer in einer speziellen Namespace für die Design-bezogenen Typen reserviert.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. Definieren Sie den Konstruktor für die `MarqueeControlRootDesigner` Klasse. Fügen Sie eine <xref:System.Diagnostics.Trace.WriteLine%2A> -Anweisung in den Text des Konstruktors. Dies wird zu Debugzwecken nützlich sein.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="creating-an-instance-of-your-custom-control"></a>Erstellen einer Instanz des benutzerdefinierten Steuerelements
 Um das benutzerdefinierte während der Entwurfszeit Verhalten des Steuerelements zu beobachten, setzen Sie eine Instanz des Steuerelements im Formular in `MarqueeControlTest` Projekt.

### <a name="to-create-an-instance-of-your-custom-control"></a>Zum Erstellen einer Instanz des benutzerdefinierten Steuerelements

1. Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die `MarqueeControlTest` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "DemoMarqueeControl."

2. Öffnen der `DemoMarqueeControl` Datei die **Code-Editor**. Importieren Sie am Anfang der Datei, die `MarqueeControlLibrary` Namespace:

```vb
Imports MarqueeControlLibrary
```

```csharp
using MarqueeControlLibrary;
```

1. Ändern Sie die Deklaration der `DemoMarqueeControl` das erben die `MarqueeControl` Klasse.

2. Erstellen Sie das Projekt.

3. Öffnen Sie `Form1` im Windows Forms-Designer.

4. Suchen der **MarqueeControlTest Komponenten** Registerkarte die **Toolbox** und öffnen Sie sie. Ziehen Sie eine `DemoMarqueeControl` aus der **Toolbox** auf das Formular.

5. Erstellen Sie das Projekt.

## <a name="setting-up-the-project-for-design-time-debugging"></a>Einrichten des Projekts für das Debuggen zur Entwurfszeit

Wenn Sie eine benutzerdefinierte während der Entwurfszeit-Benutzeroberfläche entwickeln, werden Debuggen Sie Ihre Steuerelemente und Komponenten erforderlich. Es ist eine einfache Möglichkeit, Ihr Projekt einzurichten, um Debuggen zur Entwurfszeit zu ermöglichen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

### <a name="to-set-up-the-project-for-design-time-debugging"></a>Zum Einrichten des Projekts für Design-Time-Debuggen

1. Mit der rechten Maustaste die `MarqueeControlLibrary` Projekt, und wählen **Eigenschaften**.

2. Wählen Sie in das Dialogfeld "MarqueeControlLibrary-Eigenschaftenseiten" die **Debuggen** Seite.

3. In der **Startaktion** wählen Sie im Abschnitt **externes Startprogramm**. Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) Schaltfläche, um für die Visual Studio-IDE navigieren. Der Name der ausführbaren Datei lautet devenv.exe aus, und wenn Sie am Standardspeicherort installiert haben, wird der Pfad ist %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.

4. Klicken Sie auf OK, um das Dialogfeld zu schließen.

5. Mit der rechten Maustaste die `MarqueeControlLibrary` Projekt, und wählen Sie "Als Startprojekt festlegen" aus, um diese Konfiguration für Remotedebugging zu ermöglichen.

## <a name="checkpoint"></a>Checkpoint

Sie können nun das Entwurfszeit-Verhalten des benutzerdefinierten Steuerelements zu debuggen. Nachdem Sie ermittelt haben, dass die debugging-Umgebung ordnungsgemäß eingerichtet ist, testen Sie die Zuordnung zwischen das benutzerdefinierte Steuerelement und dem benutzerdefinierten Designer.

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a>Zum Testen der Debugumgebung und die designerzuordnung

1. Öffnen der `MarqueeControlRootDesigner` Quelldatei in die **Code-Editor** und platzieren Sie einen Haltepunkt auf der <xref:System.Diagnostics.Trace.WriteLine%2A> Anweisung.

2. Drücken Sie F5, um die Debugsitzung zu starten. Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.

3. Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "MarqueeControlTest". Finden Sie die Projektmappe durch Auswahl **zuletzt geöffnete Projekte** aus der **Datei** Menü. Die Projektmappendatei "MarqueeControlTest.sln" wird als die zuletzt Datei verwendete aufgeführt.

4. Öffnen der `DemoMarqueeControl` im Designer. Beachten Sie, dass die Debuginstanz von Visual Studio aktiviert und die Ausführung am Haltepunkt an. Drücken Sie F5, um die Debugsitzung fortzusetzen.

An diesem Punkt ist alles, was für Sie zum Entwickeln und Debuggen das benutzerdefinierte Steuerelement und seinen zugeordneten Designer. Der Rest dieser exemplarischen Vorgehensweise wird auf die Details der Implementierung von Features des Steuerelements und dem Designer konzentrieren.

## <a name="implementing-your-custom-control"></a>Implementieren des benutzerdefinierten Steuerelements

Die `MarqueeControl` ist eine <xref:System.Windows.Forms.UserControl> mit ein wenig anpassen. Es macht zwei Methoden verfügbar: `Start`, dem die Animation beginnt und `Stop`, die die Animation beendet. Da die `MarqueeControl` enthält untergeordnete Steuerelemente, die implementieren die `IMarqueeWidget` -Schnittstelle, `Start` und `Stop` aufzählen jedes untergeordnete Steuerelement und rufen die `StartMarquee` und `StopMarquee` Methoden auf jedes untergeordnete Steuerelement bzw. implementiert `IMarqueeWidget`.

Die Darstellung der `MarqueeBorder` und `MarqueeText` Steuerelemente ist abhängig von das Layout an, damit `MarqueeControl` überschreibt der <xref:System.Windows.Forms.Control.OnLayout%2A> -Methode und ruft <xref:System.Windows.Forms.Control.PerformLayout%2A> auf untergeordnete Steuerelemente von diesem Typ.

Dies ist das Ausmaß der der `MarqueeControl` Anpassungen. Die Run-Time-Features werden von implementiert die `MarqueeBorder` und `MarqueeText` Steuerelemente und die Design-Time-Features werden von implementiert die `MarqueeBorderDesigner` und `MarqueeControlRootDesigner` Klassen.

### <a name="to-implement-your-custom-control"></a>Um Ihr benutzerdefiniertes Steuerelement zu implementieren.

1. Öffnen der `MarqueeControl` Quelldatei in die **Code-Editor**. Implementieren der `Start` und `Stop` Methoden.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnLayout%2A>-Methode.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="creating-a-child-control-for-your-custom-control"></a>Erstellen ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement

Die `MarqueeControl` hostet zwei Arten des untergeordneten Steuerelements: die `MarqueeBorder` Steuerelement und die `MarqueeText` Steuerelement.

- `MarqueeBorder`: Dieses Steuerelement zeichnet einen Rahmen mit "Lichtern", um seinen Rändern. Die LED blinkt nacheinander, damit sie angezeigt werden, um den Rahmen verschieben. Die Geschwindigkeit an, an dem die Lichter Flash, wird gesteuert, durch eine Eigenschaft namens `UpdatePeriod`. Mehrere andere benutzerdefinierten Eigenschaften bestimmen, andere Aspekte der Darstellung des Steuerelements. Zwei Methoden, nämlich `StartMarquee` und `StopMarquee`, steuern, wann die Animation wird gestartet und beendet.

- `MarqueeText`: Dieses Steuerelement zeichnet eine blinkende Zeichenfolge. Wie die `MarqueeBorder` -Steuerelement, die Geschwindigkeit, mit der der Text aufblinkt, wird gesteuert, indem die `UpdatePeriod` Eigenschaft. Die `MarqueeText` -Steuerelement verfügt auch über die `StartMarquee` und `StopMarquee` Methoden gemeinsam mit der `MarqueeBorder` Steuerelement.

Zur Entwurfszeit die `MarqueeControlRootDesigner` können Sie diese beiden Steuerelementtypen hinzugefügt werden eine `MarqueeControl` in beliebiger Kombination.

Allgemeine Funktionen der beiden Steuerelemente sind in der eine Schnittstelle namens berücksichtigt `IMarqueeWidget`. Dadurch wird die `MarqueeControl` Marquee-bezogene untergeordnete Steuerelemente zu ermitteln und diese besondere Behandlung.

Um das Animationsfeature für regelmäßige zu implementieren, verwenden Sie <xref:System.ComponentModel.BackgroundWorker> Objekte aus der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace. Sie können <xref:System.Windows.Forms.Timer> Objekte, wenn jedoch viele `IMarqueeWidget` Objekte vorhanden sind, die einzelnen UI-Thread ist möglicherweise nicht mit der Animation zu halten.

### <a name="to-create-a-child-control-for-your-custom-control"></a>Um ein untergeordnetes Steuerelement für das benutzerdefinierte Steuerelement zu erstellen.

1. Eine neue Klasse zum Hinzufügen der `MarqueeControlLibrary` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "IMarqueeWidget."

2. Öffnen der `IMarqueeWidget` Quelldatei in die **Code-Editor** und ändern Sie die Deklaration von `class` zu `interface`:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. Fügen Sie den folgenden Code der `IMarqueeWidget` verfügbar gemacht werden zwei Methoden und eine Eigenschaft, die die Animation bearbeitet:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. Fügen Sie einen neuen **benutzerdefiniertes Steuerelement** Element für die `MarqueeControlLibrary` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "MarqueeText."

5. Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> -Komponente aus der **Toolbox** auf Ihre `MarqueeText` Steuerelement. Diese Komponente ermöglicht die `MarqueeText` Steuerelement selbst asynchron aktualisiert.

6. Legen Sie im Fenster Eigenschaften die <xref:System.ComponentModel.BackgroundWorker> Komponente `WorkerReportsProgress` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaften `true`. Mit diesen Einstellungen können die <xref:System.ComponentModel.BackgroundWorker> Komponente zum Auslösen von in regelmäßigen Abständen die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis und asynchrone Updates abgebrochen. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

7. Öffnen der `MarqueeText` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces ein:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. Ändern Sie die Deklaration der `MarqueeText` zu vererben <xref:System.Windows.Forms.Label> und zum Implementieren der `IMarqueeWidget` Schnittstelle:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren sie im Konstruktor. Die `isLit` Feld bestimmt, ob der Text ist in der vorgegebenen durch Farbe gezeichnet werden die `LightColor` Eigenschaft.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die `StartMarquee` und `StopMarquee` Aufrufen von Methoden der <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden zum Starten und beenden die Animation.

    Die <xref:System.ComponentModel.CategoryAttribute.Category%2A> und <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribute gelten für die `UpdatePeriod` Eigenschaft, sodass er in einem benutzerdefinierten Abschnitt des Fensters Eigenschaften namens "Marquee." angezeigt wird.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. Implementieren Sie die Eigenschaftenaccessoren. Sie werden zwei Eigenschaften für Clients verfügbar zu machen: `LightColor` und `DarkColor`. Die <xref:System.ComponentModel.CategoryAttribute.Category%2A> und <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> Attribute werden auf diese Eigenschaften angewendet, sodass die Eigenschaften in einem benutzerdefinierten Abschnitt des Fensters Eigenschaften namens "Marquee." angezeigt werden

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. Implementieren Sie die Handler für die <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.

    Die <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler wartet die angegebene Anzahl von Millisekunden von `UpdatePeriod` löst dann die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis, bis der Code die Animation durch den Aufruf beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> -Ereignishandler schaltet den Text zwischen den hellen und dunklen Zustand Geben Sie die Darstellung der blinken.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, um die Animation zu aktivieren.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. Drücken Sie F6, um die Projektmappe zu erstellen.

## <a name="create-the-marqueeborder-child-control"></a>Erstellen des untergeordneten MarqueeBorder-Steuerelements

Die `MarqueeBorder` Steuerelement ist etwas komplexer als die `MarqueeText` Steuerelement. Sie verfügt über mehr Eigenschaften und die Animation in der <xref:System.Windows.Forms.Control.OnPaint%2A> Methode ist etwas komplexer. Im Prinzip ist es sehr ähnlich, mit der `MarqueeText` Steuerelement.

Da die `MarqueeBorder` Steuerelement kann die untergeordneten Steuerelemente haben, muss Sie achten <xref:System.Windows.Forms.Control.Layout> Ereignisse.

### <a name="to-create-the-marqueeborder-control"></a>Beim Erstellen des Steuerelements MarqueeBorder

1. Fügen Sie einen neuen **benutzerdefiniertes Steuerelement** Element für die `MarqueeControlLibrary` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "MarqueeBorder."

2. Ziehen Sie eine <xref:System.ComponentModel.BackgroundWorker> -Komponente aus der **Toolbox** auf Ihre `MarqueeBorder` Steuerelement. Diese Komponente ermöglicht die `MarqueeBorder` Steuerelement selbst asynchron aktualisiert.

3. Legen Sie im Fenster Eigenschaften die <xref:System.ComponentModel.BackgroundWorker> Komponente `WorkerReportsProgress` und <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> Eigenschaften `true`. Mit diesen Einstellungen können die <xref:System.ComponentModel.BackgroundWorker> Komponente zum Auslösen von in regelmäßigen Abständen die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis und asynchrone Updates abgebrochen. Weitere Informationen finden Sie unter [BackgroundWorker-Komponente](backgroundworker-component.md).

4. Klicken Sie im Eigenschaftenfenster auf die Schaltfläche "Ereignisse". Fügen Sie Handler für die <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.

5. Öffnen der `MarqueeBorder` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces ein:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. Ändern Sie die Deklaration der `MarqueeBorder` zu vererben <xref:System.Windows.Forms.Panel> und zum Implementieren der `IMarqueeWidget` Schnittstelle.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. Deklarieren Sie zwei Enumerationen für die Verwaltung der `MarqueeBorder` Zustand des Steuerelements: `MarqueeSpinDirection`, welche die Richtung, in dem die Lichter "um den Rahmen, und `MarqueeLightShape`, bestimmt die Form der Lichter (quadratische oder zirkuläre). Platzieren Sie diese Deklarationen, bevor Sie die `MarqueeBorder` Klassendeklaration.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. Deklarieren Sie die Instanzvariablen, die den verfügbar gemachten Eigenschaften entsprechen, und initialisieren sie im Konstruktor.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. Implementieren Sie die `IMarqueeWidget`-Schnittstelle.

    Die `StartMarquee` und `StopMarquee` Aufrufen von Methoden der <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> und <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> Methoden zum Starten und beenden die Animation.

    Da die `MarqueeBorder` Steuerelement kann die untergeordneten Steuerelemente enthalten die `StartMarquee` Methode listet alle untergeordneten Steuerelemente und Aufrufe `StartMarquee` auf die implementieren `IMarqueeWidget`. Die `StopMarquee` Methode verfügt über eine ähnliche Implementierung.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. Implementieren Sie die Eigenschaftenaccessoren. Die `MarqueeBorder` Steuerelement besitzt mehrere Eigenschaften steuern die Darstellung.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. Implementieren Sie die Handler für die <xref:System.ComponentModel.BackgroundWorker> Komponente <xref:System.ComponentModel.BackgroundWorker.DoWork> und <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignisse.

    Die <xref:System.ComponentModel.BackgroundWorker.DoWork> Ereignishandler wartet die angegebene Anzahl von Millisekunden von `UpdatePeriod` löst dann die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignis, bis der Code die Animation durch den Aufruf beendet <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.

    Die <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> Ereignishandler erhöht die Position des Lichts "base", aus dem der hellen/dunklen Status der anderen Lichter bestimmt ist, und ruft die <xref:System.Windows.Forms.Control.Refresh%2A> Methode, um das Steuerelement sich selbst neu zeichnet.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. Implementieren Sie die Hilfemethoden `IsLit` und `DrawLight`.

    Die `IsLit` Methode bestimmt die Farbe eines Lichts an einer bestimmten Position. Beleuchtung, die "markiert sind" in der vorgegebenen durch Farbe gezeichnet werden die `LightColor` -Eigenschaft, und solche, die "dunklen" sind in der vorgegebenen durch Farbe gezeichnet werden die `DarkColor` Eigenschaft.

    Die `DrawLight` Methode zeichnet ein Licht mithilfe der entsprechenden Farbe, Form und Position.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. Überschreiben der <xref:System.Windows.Forms.Control.OnLayout%2A> und <xref:System.Windows.Forms.Control.OnPaint%2A> Methoden.

    Die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode zeichnet die Lichter an den Rändern der `MarqueeBorder` Steuerelement.

    Da die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, die die Abmessungen des hängt die `MarqueeBorder` -Steuerelement, müssen Sie sie aufrufen, sobald das Layout geändert wird. Um dies zu erreichen, außer Kraft setzen <xref:System.Windows.Forms.Control.OnLayout%2A> , und rufen Sie <xref:System.Windows.Forms.Control.Refresh%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a>Erstellen eines benutzerdefinierten Designers Schatten und Filtereigenschaften

Die `MarqueeControlRootDesigner` Klasse stellt die Implementierung für den Stamm-Designer. Zusätzlich zu diesem Designer, der die benutzerzertifikatauthentifizierung die `MarqueeControl`, benötigen Sie einen benutzerdefinierten Designer, der speziell zugeordnet ist die `MarqueeBorder` Steuerelement. Dieser Designer stellt benutzerdefiniertes Verhalten, das im Rahmen der benutzerdefinierten Stamm-Designer geeignet ist.

Insbesondere die `MarqueeBorderDesigner` "Beschatten" und Filtern Sie nach bestimmten Eigenschaften wird die `MarqueeBorder` Steuerelement, das ihre Interaktion mit der entwurfsumgebung ändern.

Abfangen von Aufrufen von einer Komponente-Eigenschaftenaccessor wird als "shadowing." bezeichnet. Es ermöglicht einem Designer zum Nachverfolgen des Wert, der vom Benutzer festgelegt wird, und übergeben Sie optional den Wert der entworfenen Komponente.

In diesem Beispiel die <xref:System.Windows.Forms.Control.Visible%2A> und <xref:System.Windows.Forms.Control.Enabled%2A> werden Eigenschaften durch ein Shadowing ausgeführt werden die `MarqueeBorderDesigner`, die verhindert, dass die Benutzer können die `MarqueeBorder` Steuerelement unsichtbar oder deaktiviert, während der Entwurfszeit.

Designer können auch hinzufügen und Entfernen von Eigenschaften. In diesem Beispiel die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft wird zur Entwurfszeit entfernt werden, da die `MarqueeBorder` Steuerelement programmgesteuert festgelegt, der die Auffüllung basierend auf der Größe der Lichter durch die `LightSize` Eigenschaft.

Die Basisklasse für `MarqueeBorderDesigner` ist <xref:System.ComponentModel.Design.ComponentDesigner>, das hat es sich um Methoden, die die Attribute, Eigenschaften und Ereignisse verfügbar gemacht werden von einem Steuerelement zur Entwurfszeit ändern können:

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

Wenn Sie die öffentliche Schnittstelle einer Komponente, die mit diesen Methoden ändern, müssen Sie die folgenden Regeln einhalten:

- Hinzufügen oder Entfernen von Elementen in der `PreFilter` nur Methoden

- Ändern Sie vorhandene Elemente in der `PostFilter` nur Methoden

- Rufen Sie die basisimplementierung immer zuerst die `PreFilter` Methoden

- Rufen Sie die basisimplementierung immer zuletzt die `PostFilter` Methoden

Die folgenden Regeln einhalten wird sichergestellt, dass alle Designer in der Umgebung zur Entwurfszeit eine konsistente Sicht aller Komponenten entworfen wird.

Die <xref:System.ComponentModel.Design.ComponentDesigner> -Klasse stellt ein Wörterbuch für die Verwaltung von die Werte der Eigenschaften, die Shadowing durchgeführt wurde, sodass Sie keine bestimmte Nachrichteninstanzvariablen erstellen zu müssen.

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a>Erstellen ein benutzerdefiniertes Designers für Schattenkopien und filter

1. Mit der rechten Maustaste die **Entwurf** Ordner, und fügen Sie eine neue Klasse hinzu. Benennen Sie der Quelldatei Basis von "MarqueeBorderDesigner."

2. Öffnen der `MarqueeBorderDesigner` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei die folgenden Namespaces ein:

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. Ändern Sie die Deklaration der `MarqueeBorderDesigner` zu vererben <xref:System.Windows.Forms.Design.ParentControlDesigner>.

    Da die `MarqueeBorder` Steuerelement die untergeordneten Steuerelemente enthalten kann `MarqueeBorderDesigner` erbt <xref:System.Windows.Forms.Design.ParentControlDesigner>, behandelt die über-und untergeordneten Aktivität.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. Überschreiben die basisimplementierung der <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. Implementieren Sie die <xref:System.Windows.Forms.Control.Enabled%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Visible%2A>-Eigenschaft. Diese Implementierungen Shadowing für Eigenschaften des Steuerelements.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handling-component-changes"></a>Behandeln Änderungen an der Clientkomponenten
 Die `MarqueeControlRootDesigner` Klasse enthält die benutzerdefinierte während der Entwurfszeit-Erfahrung für Ihre `MarqueeControl` Instanzen. Die meisten Funktionen während der Entwurfszeit wird geerbt von der <xref:System.Windows.Forms.Design.DocumentDesigner> -Klasse, die Ihr Code werden zwei spezielle Anpassungen zu implementieren: Verarbeitung von Änderungen an der Clientkomponenten und die Designerverben hinzufügen.

 Als Benutzern beim Entwerfen ihrer `MarqueeControl` -Instanzen, die Ihre Stamm-Designer wird überwacht Änderungen an der `MarqueeControl` und seine untergeordneten Steuerelemente. Die entwurfszeitumgebung stellt einen geeigneten Dienst, <xref:System.ComponentModel.Design.IComponentChangeService>für nachverfolgung Komponente Zustand ändert.

 Sie erhalten einen Verweis auf diesen Dienst, durch Abfragen der Umgebung mit der <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> Methode. Wenn die Abfrage erfolgreich ist, kann Designer anfügen ein Handlers für die <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> Ereignis und führen Sie alle Aufgaben zum Erhaltung des konsistenten Zustands zur Entwurfszeit erforderlich sind.

 Im Fall von der `MarqueeControlRootDesigner` -Klasse, rufen Sie die <xref:System.Windows.Forms.Control.Refresh%2A> -Methode für jede `IMarqueeWidget` enthaltene Objekt das `MarqueeControl`. Dies bewirkt, dass die `IMarqueeWidget` Objekt sich selbst entsprechend neu zeichnet, wenn Eigenschaften des übergeordneten Elements wie <xref:System.Windows.Forms.Control.Size%2A> geändert werden.

### <a name="to-handle-component-changes"></a>So behandeln Sie komponentenänderungen

1. Öffnen der `MarqueeControlRootDesigner` Quelldatei in die **Code-Editor** und überschreiben die <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode. Rufen Sie die basisimplementierung für <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> und Abfragen für die <xref:System.ComponentModel.Design.IComponentChangeService>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. Implementieren der <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> -Ereignishandler. Testen Sie die sendende Komponente, und es ist ein `IMarqueeWidget`, rufen Sie die <xref:System.Windows.Forms.Control.Refresh%2A> Methode.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="adding-designer-verbs-to-your-custom-designer"></a>Hinzufügen von Designerverben zu Ihrem benutzerdefinierten Designer

Ein Designerverb ist ein mit einem Ereignishandler verknüpfter Menübefehl. Designerverben werden Kontextmenü einer Komponente zur Entwurfszeit hinzugefügt. Weitere Informationen finden Sie unter <xref:System.ComponentModel.Design.DesignerVerb>.

Sie werden den Designern zwei Designerverben hinzufügen: **Test ausführen** und **beenden Test**. Diese Verben ermöglichen Sie das Laufzeitverhalten des Anzeigen der `MarqueeControl` zur Entwurfszeit. Diese Verben werden hinzugefügt, die `MarqueeControlRootDesigner`.

Bei **Test ausführen** wird aufgerufen, der Verb-Ereignishandler ruft die `StartMarquee` Methode für die `MarqueeControl`. Bei **Test beenden** wird aufgerufen, der Verb-Ereignishandler ruft die `StopMarquee` Methode für die `MarqueeControl`. Die Implementierung der `StartMarquee` und `StopMarquee` Methoden Aufrufen dieser Methoden für enthaltene Steuerelemente, die implementieren `IMarqueeWidget`, sodass jedes enthaltene `IMarqueeWidget` Steuerelemente im Test ebenfalls einbezogen werden.

### <a name="to-add-designer-verbs-to-your-custom-designers"></a>So fügen den benutzerdefinierten Designern Designerverben hinzu

1. In der `MarqueeControlRootDesigner` -Klasse verwenden, fügen Sie Ereignishandler mit dem Namen `OnVerbRunTest` und `OnVerbStopTest`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. Verbinden Sie diese Ereignishandler mit den entsprechenden Designerverben an. `MarqueeControlRootDesigner` erbt einen <xref:System.ComponentModel.Design.DesignerVerbCollection> von der Basisklasse. Erstellen Sie zwei neue <xref:System.ComponentModel.Design.DesignerVerb> -Objekte und fügen sie dieser Auflistung in der <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> Methode.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="creating-a-custom-uitypeeditor"></a>Erstellen eine benutzerdefinierte UITypeEditor

Wenn Sie eine benutzerdefinierte während der Entwurfszeit-Erfahrung für Benutzer erstellen, ist es oft wünschenswert, eine benutzerdefinierte Aktivität mit dem Fenster "Eigenschaften" erstellen. Sie erreichen dies durch das Erstellen einer <xref:System.Drawing.Design.UITypeEditor>. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Typeditor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fd3kt7d5(v=vs.120)).

Die `MarqueeBorder` Steuerelement macht mehrere Eigenschaften im Eigenschaftenfenster verfügbar. Zwei dieser Eigenschaften `MarqueeSpinDirection` und `MarqueeLightShape` durch Enumerationen dargestellt werden. Veranschaulicht die Verwendung von einer UI-Typ-Editor die `MarqueeLightShape` Eigenschaft weist eine zugeordnete <xref:System.Drawing.Design.UITypeEditor> Klasse.

### <a name="to-create-a-custom-ui-type-editor"></a>So erstellen einen benutzerdefinierte UI-Typ-editor

1. Öffnen der `MarqueeBorder` Quelldatei in die **Code-Editor**.

2. In der Definition der `MarqueeBorder` Klasse, deklarieren Sie eine Klasse namens `LightShapeEditor` abgeleitet, die <xref:System.Drawing.Design.UITypeEditor>.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable mit dem Namen `editorService`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>-Methode. Diese Implementierung gibt <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, wodurch angewiesen wird, der entwurfsumgebung Vorgehensweise beim Anzeigen der `LightShapeEditor`.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. Überschreiben Sie die <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>-Methode. Diese Implementierung fragt die entwurfsumgebung für eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Objekt. Wenn erfolgreich, er erstellt eine `LightShapeSelectionControl`. Die <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> Methode wird aufgerufen, um das Starten der `LightShapeEditor`. Der Rückgabewert von diesem Aufruf wird die entwurfsumgebung zurückgegeben.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a>Erstellen ein Steuerelement für Ihre benutzerdefinierte UITypeEditor

1. Die `MarqueeLightShape` Eigenschaft unterstützt zwei Arten von Licht Shapes: `Square` und `Circle`. Erstellen Sie ein benutzerdefiniertes Steuerelement, das ausschließlich zum Zweck der Anzeige dieser Werte im Fenster Eigenschaften verwendet. Dieses benutzerdefinierte Steuerelement verwendet werden durch Ihre <xref:System.Drawing.Design.UITypeEditor> für die Interaktion mit dem Fenster "Eigenschaften".

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a>So erstellen einem Steuerelement für die benutzerdefinierte Benutzeroberfläche Typ-editor

1. Fügen Sie einen neuen <xref:System.Windows.Forms.UserControl> Element für die `MarqueeControlLibrary` Projekt. Weisen Sie der neuen Quelldatei Basisnamen "LightShapeSelectionControl."

2. Ziehen Sie zwei <xref:System.Windows.Forms.Panel> -Steuerelemente aus der **Toolbox** auf die `LightShapeSelectionControl`. Nennen Sie diese `squarePanel` und `circlePanel`. Ordnen Sie sie nebeneinander an. Legen Sie die <xref:System.Windows.Forms.Control.Size%2A> -Eigenschaft beider <xref:System.Windows.Forms.Panel> -Steuerelementen an (60, 60). Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft der `squarePanel` zu steuern (8, 10). Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft der `circlePanel` die Steuerung an ("80", "10"). Legen Sie schließlich die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft der `LightShapeSelectionControl` auf (150, 80).

3. Öffnen der `LightShapeSelectionControl` Quelldatei in die **Code-Editor**. Importieren Sie am Anfang der Datei, die <xref:System.Windows.Forms.Design?displayProperty=nameWithType> Namespace:

```vb
Imports System.Windows.Forms.Design
```

```csharp
using System.Windows.Forms.Design;
```

1. Implementieren <xref:System.Windows.Forms.Control.Click> -Ereignishandlern für die `squarePanel` und `circlePanel` Steuerelemente. Diese Methoden rufen <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> zum Beenden des benutzerdefiniertes <xref:System.Drawing.Design.UITypeEditor> -offlinebearbeitungssitzung zu starten.

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

2. Deklarieren Sie eine <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> Instanzvariable mit dem Namen `editorService`.

```vb
Private editorService As IWindowsFormsEditorService
```

```csharp
private IWindowsFormsEditorService editorService;
```

1. Deklarieren Sie eine `MarqueeLightShape` Instanzvariable mit dem Namen `lightShapeValue`.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

2. In der `LightShapeSelectionControl` -Konstruktor, fügen Sie der <xref:System.Windows.Forms.Control.Click> Ereignishandler die `squarePanel` und `circlePanel` Steuerelemente <xref:System.Windows.Forms.Control.Click> Ereignisse. Darüber hinaus definieren Sie eine Überladung des Konstruktors, der zugewiesen der `MarqueeLightShape` Wert über die entwurfsumgebung für die `lightShapeValue` Feld.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

3. In der <xref:System.ComponentModel.Component.Dispose%2A> -Methode, trennen Sie die <xref:System.Windows.Forms.Control.Click> -Ereignishandler.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

4. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**. Öffnen Sie die Datei LightShapeSelectionControl.Designer.cs oder LightShapeSelectionControl.Designer.vb-Datei, und entfernen Sie die Standarddefinition des der <xref:System.ComponentModel.Component.Dispose%2A> Methode.

5. Implementiert die `LightShape`-Eigenschaft.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

6. Überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode. Diese Implementierung wird ein ausgefülltes Quadrat und der Kreis gezeichnet. Es wird auch den ausgewählten Wert hervorheben, durch Zeichnen eines Rahmens um eine Form vom Typ oder die andere.

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="testing-your-custom-control-in-the-designer"></a>Testen das benutzerdefinierte Steuerelement im Designer

An diesem Punkt können Sie erstellen die `MarqueeControlLibrary` Projekt. Testen Sie die Implementierung durch Erstellen eines Steuerelements, die von erbt die `MarqueeControl` -Klasse und verwenden es in einem Formular.

### <a name="to-create-a-custom-marqueecontrol-implementation"></a>Erstellen Sie eine benutzerdefinierte Implementierung der MarqueeControl

1. Öffnen Sie `DemoMarqueeControl` im Windows Forms-Designer. Dies erstellt eine Instanz der `DemoMarqueeControl` geben, und zeigt ihn in einer Instanz von der `MarqueeControlRootDesigner` Typ.

2. In der **Toolbox**öffnen die **MarqueeControlLibrary Komponenten** Registerkarte. Sie sehen die `MarqueeBorder` und `MarqueeText` Steuerelemente zur Auswahl zur Verfügung.

3. Ziehen Sie eine Instanz von der `MarqueeBorder` -Steuerelement auf die `DemoMarqueeControl` Entwurfsoberfläche. Docken Sie dieses `MarqueeBorder` Steuerelement an das übergeordnete Steuerelement.

4. Ziehen Sie eine Instanz von der `MarqueeText` -Steuerelement auf die `DemoMarqueeControl` Entwurfsoberfläche.

5. Erstellen Sie die Projektmappe.

6. Mit der rechten Maustaste die `DemoMarqueeControl` , und wählen Sie in der Verknüpfung im Menü der **Test ausführen** Option aus, um die Animation zu starten. Klicken Sie auf **Test beenden** die Animation beendet.

7. Öffnen Sie **Form1** in der Designansicht.

8. Platzieren Sie zwei <xref:System.Windows.Forms.Button> Steuerelemente im Formular. Nennen Sie diese `startButton` und `stopButton`, und ändern Sie die <xref:System.Windows.Forms.Control.Text%2A> Eigenschaftswerte **starten** und **beenden**bzw.

9. Implementieren <xref:System.Windows.Forms.Control.Click> -Ereignishandlern für beide <xref:System.Windows.Forms.Button> Steuerelemente.

10. In der **Toolbox**öffnen die **MarqueeControlTest Komponenten** Registerkarte. Sie sehen die `DemoMarqueeControl` zur Auswahl zur Verfügung.

11. Ziehen Sie eine Instanz des `DemoMarqueeControl` auf die **Form1** Entwurfsoberfläche.

12. In der <xref:System.Windows.Forms.Control.Click> Ereignishandler Aufrufen der `Start` und `Stop` Methoden für die `DemoMarqueeControl`.

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

1. Legen Sie die `MarqueeControlTest` -Projekt als Startprojekt fest, und führen Sie sie. Sie sehen, dass die Anzeige des Formulars Ihre `DemoMarqueeControl`. Klicken Sie auf die **starten** Schaltfläche, um die Animation zu starten. Sie sollten den Text blinken und die Lichter, um den Rahmen angezeigt werden.

## <a name="next-steps"></a>Nächste Schritte

Die `MarqueeControlLibrary` veranschaulicht eine einfache Implementierung von benutzerdefinierten Steuerelementen und den zugeordneten Designer. Sie können dieses Beispiel auf verschiedene Weise komplexere vornehmen:

- Ändern Sie die Eigenschaftswerte für die `DemoMarqueeControl` im Designer. Fügen Sie weitere `MarqueBorder` Steuerelemente und docken Sie sie innerhalb ihrer übergeordneten-Instanzen, um einen verschachtelten Effekt zu erstellen. Experimentieren Sie mit verschiedenen Einstellungen für die `UpdatePeriod` und die Light-bezogene Eigenschaften.

- Erstellen Sie eigene Implementierungen von `IMarqueeWidget`. Sie könnten z. B. ein blinkendes "Neon anmelden" oder ein animiertes Symbol mit mehreren Abbildern erstellen.

- Weiter passen Sie an, die während der Entwurfszeit-Benutzeroberfläche. Sie können versuchen, mehr Eigenschaften als shadowing <xref:System.Windows.Forms.Control.Enabled%2A> und <xref:System.Windows.Forms.Control.Visible%2A>, und neue Eigenschaften hinzufügen. Fügen Sie neue Designerverben um häufige Aufgaben wie das Andocken von untergeordneten Steuerelemente zu vereinfachen.

- Lizenz die `MarqueeControl`. Weitere Informationen finden Sie unter [Vorgehensweise: Lizenzieren von Komponenten und Steuerelementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120)).

- Steuern Sie, wie die Steuerelemente serialisiert werden und wie Code für sie generiert wird. Weitere Informationen finden Sie unter [dynamische Quelle-Codegenerierung und-Kompilierung](../../reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
- [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das Entwurfszeitfeatures nutzt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))
- [Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Benutzerdefinierte Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h51z5c0x(v=vs.120))
