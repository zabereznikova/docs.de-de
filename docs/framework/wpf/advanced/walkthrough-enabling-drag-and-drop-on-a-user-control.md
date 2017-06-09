---
title: "Exemplarische Vorgehensweise: Aktivieren der Drag &amp; Drop-Funktion auf einem Benutzersteuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Drag & Drop [WPF], Exemplarische Vorgehensweise"
  - "Exemplarische Vorgehensweise [WPF], Drag &amp; Drop"
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Exemplarische Vorgehensweise: Aktivieren der Drag &amp; Drop-Funktion auf einem Benutzersteuerelement
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie ein benutzerdefiniertes Benutzersteuerelement erstellen, das bei der Drag & Drop\-Datenübertragung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verwendet werden kann.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie ein benutzerdefiniertes WPF\-<xref:System.Windows.Controls.UserControl>, das eine Kreisform darstellt.  Sie implementieren Funktionen für das Steuerelement, um die Datenübertragung mittels Drag & Drop zu ermöglichen.  Wenn Sie z. B. ein Kreissteuerelement auf ein anderes ziehen, werden Füllfarbendaten aus dem Quellkreis in das Ziel kopiert.  Wenn Sie ein Kreissteuerelement auf ein <xref:System.Windows.Controls.TextBox> ziehen, wird die Zeichenfolgendarstellung der Füllfarbe in das <xref:System.Windows.Controls.TextBox> kopiert.  Außerdem erstellen Sie eine kleine Anwendung, die zwei Bereichssteuerelemente und ein <xref:System.Windows.Controls.TextBox> enthält, um die Drag & Drop\-Funktion zu testen.  Sie schreiben Code, der den Bereichen das Verarbeiten abgelegter Kreisdaten ermöglicht, sodass Sie Kreise aus der Auflistung der untergeordneten Elemente eines Bereichs in den anderen Bereich verschieben oder kopieren können.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen eines benutzerdefinierten Benutzersteuerelements  
  
-   Einrichten des Benutzersteuerelements als Quelle des Ziehvorgangs  
  
-   Einrichten des Benutzersteuerelements als Ablageziel  
  
-   Einrichten eines Bereichs zum Empfangen abgelegter Daten des Benutzersteuerelements  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio 2010  
  
## Erstellen des Anwendungsprojekts  
 In diesem Abschnitt erstellen Sie die Anwendungsinfrastruktur, die eine Hauptseite mit zwei Bereichen und ein <xref:System.Windows.Controls.TextBox> enthält.  
  
### So erstellen Sie das Projekt  
  
1.  Erstellen Sie in Visual Basic oder Visual C\# ein neues WPF\-Anwendungsprojekt mit dem Namen `DragDropExample`.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Anwendungsprojekts](http://msdn.microsoft.com/de-de/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Öffnen Sie MainWindow.xaml.  
  
3.  Fügen Sie das folgende Markup zwischen den öffnenden und schließenden <xref:System.Windows.Controls.Grid>\-Tags hinzu.  
  
     Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## Hinzufügen eines neuen Benutzersteuerelements zum Projekt  
 In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.  
  
### So fügen Sie ein neues Benutzersteuerelement hinzu  
  
1.  Klicken Sie im Menü "Projekt" auf **Benutzersteuerelement hinzufügen**.  
  
2.  Ändern Sie im Dialogfeld "Neues Element hinzufügen" den Namen in `Circle.xaml`, und klicken Sie auf **Hinzufügen**.  
  
     "Circle.xaml" und die zugehörige CodeBehind\-Datei werden dem Projekt hinzugefügt.  
  
3.  Öffnen Sie "Circle.xaml".  
  
     Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.  
  
4.  Fügen Sie dem Stamm\-<xref:System.Windows.Controls.Grid> das folgende Markup hinzu, um ein einfaches Benutzersteuerelement mit einem blauen Kreis als Benutzeroberfläche zu erstellen.  
  
     [!code-xml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
6.  Fügen Sie in C\# den folgenden Code nach dem Standardkonstruktor hinzu, um einen Kopierkonstruktor zu erstellen.  Fügen Sie in Visual Basic den folgenden Code hinzu, um einen Standardkonstruktor und einen Kopierkonstruktor zu erstellen.  
  
     Damit das Benutzersteuerelement kopiert werden kann, fügen Sie in der CodeBehind\-Datei eine Kopierkonstruktormethode hinzu.  Im vereinfachten Kreisbenutzersteuerelement kopieren Sie nur die Füllung und die Größe des Benutzersteuerelements.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### So fügen Sie das Benutzersteuerelement dem Hauptfenster hinzu  
  
1.  Öffnen Sie MainWindow.xaml.  
  
2.  Fügen Sie dem öffnenden <xref:System.Windows.Window>\-Tag den folgenden XAML\-Code hinzu, um einen XML\-Namespaceverweis auf die aktuelle Anwendung zu erstellen.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  Fügen Sie im ersten <xref:System.Windows.Controls.StackPanel> den folgenden XAML\-Code hinzu, um zwei Instanzen des Kreisbenutzersteuerelements im ersten Bereich zu erstellen.  
  
     [!code-xml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     Das vollständige XAML für den Bereich sieht folgendermaßen aus.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## Implementieren von Ereignissen für die Quelle des Ziehvorgangs im Benutzersteuerelement  
 In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A>\-Methode, und Sie initiieren den Drag & Drop\-Vorgang.  
  
 Wenn ein Ziehvorgang gestartet wird \(eine Maustaste wird gedrückt und die Maus wird bewegt\), verpacken Sie die zu übertragenden Daten in einem <xref:System.Windows.DataObject>.  In diesem Fall verpackt das Kreissteuerelement drei Datenelemente: eine Zeichenfolgendarstellung der Füllfarbe, eine Double\-Darstellung seiner Höhe und eine Kopie von sich selbst.  
  
### So initiieren Sie einen Drag & Drop\-Vorgang  
  
1.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
2.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnMouseMove%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.MouseMove>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     Diese <xref:System.Windows.UIElement.OnMouseMove%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Sie überprüft, ob die linke Maustaste gedrückt wird, während sich der Mauszeiger bewegt.  
  
    -   Sie verpackt Kreisdaten in einem <xref:System.Windows.DataObject>.  In diesem Fall verpackt das Kreissteuerelement drei Datenelemente: eine Zeichenfolgendarstellung der Füllfarbe, eine Double\-Darstellung seiner Höhe und eine Kopie von sich selbst.  
  
    -   Sie ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=fullName>\-Methode auf, um den Drag & Drop\-Vorgang zu initiieren.  Die folgenden drei Parameter werden an die <xref:System.Windows.DragDrop.DoDragDrop%2A>\-Methode übergeben:  
  
        -   `dragSource` – Ein Verweis auf dieses Steuerelement.  
  
        -   `data` – Das im vorherigen Code erstellte <xref:System.Windows.DataObject>.  
  
        -   `allowedEffects` – Die zulässigen Drag & Drop\-Vorgänge \(<xref:System.Windows.DragDropEffects> oder <xref:System.Windows.DragDropEffects>\).  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Klicken Sie auf eines der Kreissteuerelemente, und ziehen Sie es über die Bereiche, den anderen Kreis und das <xref:System.Windows.Controls.TextBox>.  Wenn der Kreis über das <xref:System.Windows.Controls.TextBox> gezogen wird, ändert sich die Darstellung des Cursors, um eine Verschiebung anzuzeigen.  
  
5.  Drücken Sie die STRG\-TASTE, während der Kreis über das <xref:System.Windows.Controls.TextBox> gezogen wird.  Die Darstellung des Cursors ändert sich, um einen Kopiervorgang anzuzeigen.  
  
6.  Legen Sie den Kreis per Drag & Drop auf dem <xref:System.Windows.Controls.TextBox> ab.  Die Zeichenfolgendarstellung der Füllfarbe des Kreises wird an <xref:System.Windows.Controls.TextBox> angefügt.  
  
     ![Zeichenfolgendarstellung der Füllfarbe für den Kreis](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop\_ColorString")  
  
 Standardmäßig ändert sich die Darstellung des Cursors während eines Drag & Drop\-Vorgangs, um anzugeben, welche Auswirkungen das Ablegen der Daten hat.  Sie können das Feedback für den Benutzer anpassen, indem Sie das <xref:System.Windows.UIElement.GiveFeedback>\-Ereignis behandeln und einen anderen Cursor festlegen.  
  
### So geben Sie dem Benutzer Feedback  
  
1.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
2.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnGiveFeedback%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.GiveFeedback>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     Diese <xref:System.Windows.UIElement.OnGiveFeedback%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Sie überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>\-Werte, die im <xref:System.Windows.UIElement.DragOver>\-Ereignishandler des Ablageziels festgelegt sind.  
  
    -   Sie legt basierend auf dem <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>\-Wert einen benutzerdefinierten Cursor fest.  Der Cursor soll dem Benutzer visuelles Feedback über die Auswirkungen des Ablegens der Daten geben.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Ziehen Sie eines der Kreissteuerelemente über die Bereiche, den anderen Kreis und das <xref:System.Windows.Controls.TextBox>.  Jetzt werden die benutzerdefinierten Cursor angezeigt, die Sie in der <xref:System.Windows.UIElement.OnGiveFeedback%2A>\-Überschreibung angegeben haben.  
  
     ![Drag & Drop mit benutzerdefiniertem Cursor](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop\_CustomCursor")  
  
5.  Wählen Sie den Text `green` im <xref:System.Windows.Controls.TextBox> aus.  
  
6.  Ziehen Sie den Text `green` auf ein Kreissteuerelement.  Die Standardcursor werden angezeigt, um die Auswirkungen des Drag & Drop\-Vorgangs anzugeben.  Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.  
  
## Implementieren von Ablagezielereignisse im Benutzersteuerelement  
 In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, Sie überschreiben die Methoden, die dem Benutzersteuerelement die Funktion als Ablageziel ermöglichen, und Sie verarbeiten die Daten, die auf dem Benutzersteuerelement abgelegt werden.  
  
### So richten Sie das Benutzersteuerelement als Ablageziel ein  
  
1.  Öffnen Sie "Circle.xaml".  
  
2.  Fügen Sie im öffnenden <xref:System.Windows.Controls.UserControl>\-Tag die <xref:System.Windows.UIElement.AllowDrop%2A>\-Eigenschaft hinzu, und legen Sie sie auf `true` fest.  
  
     [!code-xml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 Die <xref:System.Windows.UIElement.OnDrop%2A>\-Methode wird aufgerufen, wenn die <xref:System.Windows.UIElement.AllowDrop%2A>\-Eigenschaft auf `true` festgelegt ist und Daten aus der Quelle des Ziehvorgangs auf dem Kreisbenutzersteuerelement abgelegt werden.  In dieser Methode werden die abgelegten Daten verarbeitet und auf den Kreis angewendet.  
  
### So verarbeiten Sie die abgelegten Daten  
  
1.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
2.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnDrop%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.Drop>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     Diese <xref:System.Windows.UIElement.OnDrop%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Sie überprüft mithilfe der <xref:System.Windows.DataObject.GetDataPresent%2A>\-Methode, ob die gezogenen Daten ein Zeichenfolgenobjekt enthalten.  
  
    -   Sie extrahiert mithilfe der <xref:System.Windows.DataObject.GetData%2A>\-Methode die Zeichenfolgendaten \(sofern vorhanden\).  
  
    -   Sie versucht, die Zeichenfolge mithilfe von <xref:System.Windows.Media.BrushConverter> in einen <xref:System.Windows.Media.Brush> zu konvertieren.  
  
    -   Wenn die Konvertierung erfolgreich ist, wendet sie den Pinsel auf die <xref:System.Windows.Shapes.Shape.Fill%2A> der <xref:System.Windows.Shapes.Ellipse> an, die die Benutzeroberfläche des Kreissteuerelements bereitstellt.  
  
    -   Sie markiert das <xref:System.Windows.UIElement.Drop>\-Ereignis als behandelt.  Das Drop\-Ereignis sollte als behandelt markiert werden, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass es vom Kreisbenutzersteuerelement behandelt wurde.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Wählen Sie den Text `green` im <xref:System.Windows.Controls.TextBox> aus.  
  
5.  Ziehen Sie den Text auf ein Kreissteuerelement, und legen Sie ihn ab.  Die Farbe des Kreises ändert sich von Blau in Grün.  
  
     ![Zeichenfolge in einen Pinsel konvertieren](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop\_DropGreenText")  
  
6.  Geben Sie den Text `green` in das <xref:System.Windows.Controls.TextBox> ein.  
  
7.  Wählen Sie den Text `gre` im <xref:System.Windows.Controls.TextBox> aus.  
  
8.  Ziehen Sie ihn auf ein Kreissteuerelement, und legen Sie ihn ab.  Der Cursor ändert sich, um anzugeben, dass der Ablegevorgang zulässig ist, die Farbe des Kreises wird jedoch nicht geändert, da `gre` keine gültige Farbe ist.  
  
9. Ziehen Sie das grüne Kreissteuerelement, und legen Sie es auf dem blauen Kreissteuerelement ab.  Die Farbe des Kreises ändert sich von Blau in Grün.  Der angezeigte Cursor hängt davon ab, ob das <xref:System.Windows.Controls.TextBox> oder das Kreissteuerelement die Quelle des Ziehvorgangs ist.  
  
 Zum Einrichten eines Elements als Ablageziel müssen Sie lediglich die <xref:System.Windows.UIElement.AllowDrop%2A>\-Eigenschaft auf `true` festlegen und die abgelegten Daten verarbeiten.  Zum Verbessern der Benutzerfreundlichkeit sollten Sie jedoch auch die <xref:System.Windows.UIElement.DragEnter>\-, <xref:System.Windows.UIElement.DragLeave>\- und <xref:System.Windows.UIElement.DragOver>\-Ereignisse behandeln.  In diesen Ereignissen können Sie Überprüfungen durchführen und zusätzliches Feedback für den Benutzer bereitstellen, bevor die Daten abgelegt werden.  
  
 Wenn Daten über das Kreisbenutzersteuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob sie die gezogenen Daten verarbeiten kann.  Wenn das Steuerelement die Daten nicht verarbeiten kann, sollte es den Ablegevorgang ablehnen.  Hierzu behandeln Sie das <xref:System.Windows.UIElement.DragOver>\-Ereignis, und Sie legen die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft fest.  
  
### So überprüfen Sie, ob das Ablegen von Daten zulässig ist  
  
1.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
2.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragOver%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.DragOver>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     Diese <xref:System.Windows.UIElement.OnDragOver%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Legt die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft auf <xref:System.Windows.DragDropEffects> fest.  
  
    -   Sie führt die gleichen Überprüfungen aus, die in der <xref:System.Windows.UIElement.OnDrop%2A>\-Methode ausgeführt werden, um zu bestimmen, ob das Kreisbenutzersteuerelement die gezogenen Daten verarbeiten kann.  
  
    -   Wenn das Benutzersteuerelement die Daten verarbeiten kann, legt sie die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft auf <xref:System.Windows.DragDropEffects> oder <xref:System.Windows.DragDropEffects> fest.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Wählen Sie den Text `gre` im <xref:System.Windows.Controls.TextBox> aus.  
  
5.  Ziehen Sie den Text auf ein Kreissteuerelement.  Der Cursor ändert sich, um anzugeben, dass der Ablegevorgang nicht zulässig ist, weil `gre` keine gültige Farbe ist.  
  
 Sie können die Benutzerfreundlichkeit weiter verbessern, indem Sie eine Vorschau des Ablegevorgangs anwenden.  Für das Kreisbenutzersteuerelement überschreiben Sie die <xref:System.Windows.UIElement.OnDragLeave%2A>\- und <xref:System.Windows.UIElement.OnDragEnter%2A>\-Methoden.  Wenn die Daten über das Steuerelement gezogen werden, wird der aktuelle Hintergrund <xref:System.Windows.Shapes.Shape.Fill%2A> in einer Platzhaltervariable gespeichert.  Die Zeichenfolge wird dann in einen Pinsel konvertiert und auf die <xref:System.Windows.Shapes.Ellipse> angewendet, die die Benutzeroberfläche des Kreises bereitstellt.  Wenn die Daten aus dem Kreis gezogen werden, ohne sie abzulegen, wird wieder der ursprüngliche <xref:System.Windows.Shapes.Shape.Fill%2A>\-Wert auf den Kreis angewendet.  
  
### So zeigen Sie eine Vorschau der Auswirkungen des Drag & Drop\-Vorgangs an  
  
1.  Öffnen Sie "Circle.xaml.cs" bzw. "Circle.xaml.vb".  
  
2.  Deklarieren Sie in der Circle\-Klasse eine private <xref:System.Windows.Media.Brush>\-Variable mit dem Namen `_previousFill`, und initialisieren Sie sie mit `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragEnter%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.DragEnter>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     Diese <xref:System.Windows.UIElement.OnDragEnter%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Sie speichert die <xref:System.Windows.Shapes.Shape.Fill%2A>\-Eigenschaft der <xref:System.Windows.Shapes.Ellipse> in der `_previousFill`\-Variable.  
  
    -   Sie führt die gleichen Überprüfungen aus, die in der <xref:System.Windows.UIElement.OnDrop%2A>\-Methode ausgeführt werden, um zu bestimmen, ob die Daten in einen <xref:System.Windows.Media.Brush> konvertiert werden können.  
  
    -   Wenn die Daten in einen gültigen <xref:System.Windows.Media.Brush> konvertiert werden, wendet sie ihn auf die <xref:System.Windows.Shapes.Shape.Fill%2A> der <xref:System.Windows.Shapes.Ellipse> an.  
  
4.  Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragLeave%2A>\-Überschreibung hinzu, um eine Klassenbehandlung für das <xref:System.Windows.UIElement.DragLeave>\-Ereignis bereitzustellen.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     Diese <xref:System.Windows.UIElement.OnDragLeave%2A>\-Überschreibung führt die folgenden Aufgaben aus:  
  
    -   Sie wendet den in der `_previousFill`\-Variable gespeicherten <xref:System.Windows.Media.Brush> auf die <xref:System.Windows.Shapes.Shape.Fill%2A> der <xref:System.Windows.Shapes.Ellipse> an, die die Benutzeroberfläche des Kreisbenutzersteuerelements bereitstellt.  
  
5.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
6.  Wählen Sie den Text `green` im <xref:System.Windows.Controls.TextBox> aus.  
  
7.  Ziehen Sie den Text über ein Kreissteuerelement, ohne ihn abzulegen.  Die Farbe des Kreises ändert sich von Blau in Grün.  
  
     ![Auswirkungen eines Drag & Drop&#45;Vorgangs in der Vorschau anzeigen](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop\_PreviewEffects")  
  
8.  Ziehen Sie den Text vom Kreissteuerelement weg.  Die Farbe des Kreises ändert sich wieder von Grün in Blau.  
  
## Einrichten eines Bereichs zum Empfangen abgelegter Daten  
 In diesem Abschnitt richten Sie die Bereiche, die die Kreisbenutzersteuerelemente hosten, so ein, dass sie als Ablageziele für gezogene Kreisdaten fungieren können.  Sie implementieren Code, der es Ihnen ermöglicht, einen Kreis von einem Bereich in einen anderen zu verschieben oder eine Kopie eines Kreissteuerelements zu erstellen, indem Sie während des Ziehens und Ablegens eines Kreises die STRG\-TASTE gedrückt halten.  
  
### So richten Sie den Bereich als Ablageziel ein  
  
1.  Öffnen Sie MainWindow.xaml.  
  
2.  Fügen Sie wie im folgenden XAML\-Code dargestellt in jedem der <xref:System.Windows.Controls.StackPanel>\-Steuerelemente Handler für die <xref:System.Windows.UIElement.Drop>\- und <xref:System.Windows.UIElement.DragOver>\-Ereignisse hinzu.  Geben Sie für den <xref:System.Windows.UIElement.DragOver>\-Ereignishandler den Namen `panel_DragOver` und für den <xref:System.Windows.UIElement.Drop>\-Ereignishandler den Namen `panel_Drop` ein.  
  
     [!code-xml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Öffnen Sie "MainWindows.xaml.cs" bzw. "MainWindow.xaml.vb".  
  
4.  Fügen Sie folgenden Code für den <xref:System.Windows.UIElement.DragOver>\-Ereignishandler hinzu.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Dieser <xref:System.Windows.UIElement.DragOver>\-Ereignishandler führt die folgenden Aufgaben aus:  
  
    -   Er überprüft, ob die gezogenen Daten die "Objektdaten" enthalten, die vom Kreisbenutzersteuerelement im <xref:system.Windows.DataObject> verpackt und im Aufruf an <xref:System.Windows.DragDrop.DoDragDrop%2A> übergeben wurden.  
  
    -   Wenn die "Objektdaten" vorhanden sind, überprüft er, ob die STRG\-TASTE gedrückt wird.  
  
    -   Wenn die STRG\-TASTE gedrückt wird, legt er die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft auf <xref:System.Windows.DragDropEffects> fest.  Andernfalls legt er die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft auf <xref:System.Windows.DragDropEffects> fest.  
  
5.  Fügen Sie folgenden Code für den <xref:System.Windows.UIElement.Drop>\-Ereignishandler hinzu.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Dieser <xref:System.Windows.UIElement.Drop>\-Ereignishandler führt die folgenden Aufgaben aus:  
  
    -   Er überprüft, ob das <xref:System.Windows.UIElement.Drop>\-Ereignis bereits behandelt wurde.  Wenn z. B. ein Kreis auf einem anderen Kreis abgelegt wird, der das <xref:System.Windows.UIElement.Drop>\-Ereignis behandelt, soll das Ereignis nicht auch von dem Bereich behandelt werden, der den Kreis enthält.  
  
    -   Wenn das <xref:System.Windows.UIElement.Drop>\-Ereignis nicht behandelt wurde, überprüft er, ob die STRG\-TASTE gedrückt wird.  
  
    -   Wenn die STRG\-TASTE während <xref:System.Windows.UIElement.Drop> gedrückt wird, erstellt er eine Kopie des Kreissteuerelements und fügt sie der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung des <xref:System.Windows.Controls.StackPanel> hinzu.  
  
    -   Wenn die STRG\-TASTE nicht gedrückt wird, verschiebt er den Kreis aus der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung des übergeordneten Bereichs in die <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung des Bereichs, auf dem der Kreis abgelegt wurde.  
  
    -   Er legt die <xref:System.Windows.DragEventArgs.Effects%2A>\-Eigenschaft fest, um die <xref:System.Windows.DragDrop.DoDragDrop%2A>\-Methode darüber zu benachrichtigen, ob ein Verschiebevorgang oder ein Kopiervorgang ausgeführt wurde.  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
7.  Wählen Sie den Text `green` im <xref:System.Windows.Controls.TextBox> aus.  
  
8.  Ziehen Sie den Text über ein Kreissteuerelement, und legen Sie ihn ab.  
  
9. Ziehen Sie ein Kreissteuerelement vom linken Bereich in den rechten Bereich, und legen Sie es ab.  Der Kreis wird aus der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung des linken Bereichs entfernt und der Auflistung der untergeordneten Elemente des rechten Bereichs hinzugefügt.  
  
10. Ziehen Sie ein Kreissteuerelement von dem Bereich, in dem es sich befindet, in den anderen Bereich, und legen Sie es mit gedrückter STRG\-TASTE ab.  Der Kreis wird kopiert, und die Kopie wird der <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung des empfangenden Bereichs hinzugefügt.  
  
     ![Ziehen eines Kreises beim Drücken der Strg&#45;Taste](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop\_PanelDrop")  
  
## Siehe auch  
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)