---
title: 'Exemplarische Vorgehensweise: Aktivieren der Drag & Drop auf einem Benutzersteuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 9ffaab4115edec1fc0115b27b8904970854f79d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600673"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Exemplarische Vorgehensweise: Aktivieren der Drag & Drop auf einem Benutzersteuerelement

In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.

In dieser exemplarischen Vorgehensweise erstellen Sie eine benutzerdefinierte WPF <xref:System.Windows.Controls.UserControl> , das eine Kreisform darstellt. Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen. Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert. Wenn Sie ein Kreis-Steuerelement, ziehen Sie eine <xref:System.Windows.Controls.TextBox>, die Zeichenfolgendarstellung der Füllfarbe in kopiert die <xref:System.Windows.Controls.TextBox>. Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente enthält und eine <xref:System.Windows.Controls.TextBox> zum Testen der Drag & Drop-Funktionalität. Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

-   Erstellen eines benutzerdefinierten Steuerelements.

-   Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.

-   Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.

-   Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-application-project"></a>Erstellen des Anwendungsprojekts
 In diesem Abschnitt erstellen Sie die Anwendungsstruktur, einschließlich eine Hauptseite mit zwei Panels und einer <xref:System.Windows.Controls.TextBox>.

1.  Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie ein neues WPF-Anwendungsprojekt](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).

2.  Öffnen Sie „MainWindow.xaml“.

3.  Fügen Sie das folgende Markup zwischen die öffnenden und schließenden <xref:System.Windows.Controls.Grid> Tags.

     Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu
 In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.

1.  Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.

2.  In der **neues Element hinzufügen** Dialogfeld ändern den Namen in `Circle.xaml`, und klicken Sie auf **hinzufügen**.

     Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.

3.  Öffnen Sie Circle.xaml.

     Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.

4.  Fügen Sie das folgende Markup in das Stammverzeichnis <xref:System.Windows.Controls.Grid> ein einfaches Benutzersteuerelement zu erstellen, die über die Benutzeroberfläche ein blauer Kreis verfügt.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

6.  Fügen Sie in C# den folgenden Code nach dem Standardkonstruktor hinzu, um einen Kopierkonstruktor zu erstellen. Fügen Sie in Visual Basic den folgenden Code hinzu, um sowohl einen Standardkonstruktor als auch einen Kopierkonstruktor zu erstellen.

     Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann. Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.

     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Fügen Sie das Benutzersteuerelement dem Hauptfenster

1.  Öffnen Sie „MainWindow.xaml“.

2.  Fügen Sie den folgenden XAML an das öffnende <xref:System.Windows.Window> Tag, um eine XML-Namespace-Referenz auf die aktuelle Anwendung zu erstellen.

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3.  In der ersten <xref:System.Windows.Controls.StackPanel>, fügen Sie den folgenden XAML zum Erstellen von zwei Instanzen des Kreis-Steuerelements im ersten Bereich hinzu.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Implementieren Sie die Ereignisse der Ziehquelle im Benutzersteuerelement
 In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren den Drag & Drop-Vorgang.

 Wenn ein Ziehvorgang gestartet wird (eine Maustaste gedrückt wird, und die Maus bewegt wird), Verpacken Sie die Daten in übertragen werden eine <xref:System.Windows.DataObject>. In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Initiieren eines Drag & Drop-Vorgangs

1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnMouseMove%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.MouseMove> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Dies <xref:System.Windows.UIElement.OnMouseMove%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.

    -   Verpackt die Kreisdaten in ein <xref:System.Windows.DataObject>. In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.

    -   Ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> Methode, um den Drag & Drop-Vorgang einzuleiten. Sie übergeben die folgenden drei Parameter für die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode:

        -   `dragSource`: Ein Verweis auf dieses Steuerelement.

        -   `data` – Die <xref:System.Windows.DataObject> im vorherigen Code erstellte.

        -   `allowedEffects` – Die zulässigen Drag & Drop-Vorgänge, die <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.

3.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4.  Klicken Sie auf eines der Kreis-Steuerelemente, und ziehen Sie es über die Bereiche, die den anderen Kreis und die <xref:System.Windows.Controls.TextBox>. Beim Ziehen über die <xref:System.Windows.Controls.TextBox>, ändert sich der Cursor um eine Verschiebung anzuzeigen.

5.  Beim Ziehen eines Kreises über die <xref:System.Windows.Controls.TextBox>, drücken Sie die **STRG** Schlüssel. Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.

6.  Drag & drop ein Kreises auf die <xref:System.Windows.Controls.TextBox>. Die Zeichenfolgendarstellung der Füllfarbe des Kreises wird angefügt, um die <xref:System.Windows.Controls.TextBox>.

     ![Zeichenfolgendarstellung der Füllfarbe des Kreises](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")

Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat. Sie können anpassen, dass das Feedback an den Benutzer gegeben werden, durch Behandeln der <xref:System.Windows.UIElement.GiveFeedback> Ereignis und einen anderen Cursor festlegen.

## <a name="give-feedback-to-the-user"></a>Geben Sie Feedback an den Benutzer

1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnGiveFeedback%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.GiveFeedback> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Dies <xref:System.Windows.UIElement.OnGiveFeedback%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> , in des Ablageziels festgelegte, Werte <xref:System.Windows.UIElement.DragOver> -Ereignishandler.

    -   Legt einen benutzerdefinierten Cursor auf der Grundlage der <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Wert. Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.

3.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4.  Ziehen Sie eines der Kreis über die Bereiche, die den anderen Kreis Steuerelemente und die <xref:System.Windows.Controls.TextBox>. Beachten Sie, dass die Cursor jetzt die benutzerdefinierten Cursor, die Sie angegeben haben sind, in der <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft setzen.

     ![Drag & Drop mit benutzerdefiniertem Cursor](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5.  Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.

6.  Ziehen Sie den Text `green` auf ein Kreis-Steuerelement. Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben. Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.

## <a name="implement-drop-target-events-in-the-user-control"></a>Implementieren der Ereignisse des Ablageziels im Benutzersteuerelement
 In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs

1.  Öffnen Sie Circle.xaml.

2.  Im öffnenden <xref:System.Windows.Controls.UserControl> markieren, fügen Sie der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft, und legen Sie ihn auf `true`.

     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

Die <xref:System.Windows.UIElement.OnDrop%2A> Methode wird aufgerufen, wenn die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaftensatz auf `true` und Daten aus der Quelle des Ziehvorgangs auf das Kreis-Steuerelement abgelegt ist. In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.

### <a name="to-process-the-dropped-data"></a>So verarbeiten Sie die abgelegten Daten

1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDrop%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.Drop> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Dies <xref:System.Windows.UIElement.OnDrop%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Verwendet die <xref:System.Windows.DataObject.GetDataPresent%2A> Methode zum Überprüfen, ob die gezogenen Daten ein Zeichenfolgenobjekt enthalten.

    -   Verwendet die <xref:System.Windows.DataObject.GetData%2A> Methode, um die Zeichenfolgendaten zu extrahieren, wenn es vorhanden ist.

    -   Verwendet eine <xref:System.Windows.Media.BrushConverter> versuchen, konvertieren Sie die Zeichenfolge, die eine <xref:System.Windows.Media.Brush>.

    -   Wenn die Konvertierung erfolgreich ist, gilt den Pinsel, der <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , die die Benutzeroberfläche des Kreis-Steuerelements bereitstellt.

    -   Markiert die <xref:System.Windows.UIElement.Drop> Ereignis als behandelt. Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.

3.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4.  Wählen Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.

5.  Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab. Der Kreis ändert sich von Blau in Grün.

     ![Konvertieren einer Zeichenfolge in einen Pinsel](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6.  Geben Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.

7.  Wählen Sie den Text `gre` in die <xref:System.Windows.Controls.TextBox>.

8.  Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab. Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.

9. Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement. Der Kreis ändert sich von Blau in Grün. Beachten Sie, die angezeigte Cursor abhängig, ob davon die <xref:System.Windows.Controls.TextBox> oder der Kreis die Quelle des Ziehvorgangs.

Festlegen der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft `true` und Verarbeiten der abgelegten Daten ist nur erforderlich, um ein Element, das Ziel eines Ablegevorgangs zu aktivieren. Jedoch um eine bessere benutzererfahrung zu gewährleisten, sollten auch behandelt die <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, und <xref:System.Windows.UIElement.DragOver> Ereignisse. In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.

Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können. Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen. Behandeln Sie dazu die <xref:System.Windows.UIElement.DragOver> -Ereignis und legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>So stellen sie sicher, dass die Datenablage zulässig ist

1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragOver%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragOver> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Dies <xref:System.Windows.UIElement.OnDragOver%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.

    -   Führt die gleichen Überprüfungen, die in ausgeführt werden, die <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob das Kreis-Steuerelement die gezogenen Daten verarbeiten kann.

    -   Legt fest, wenn das Benutzersteuerelement die Daten verarbeiten kann, die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.

3.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4.  Wählen Sie den Text `gre` in die <xref:System.Windows.Controls.TextBox>.

5.  Ziehen Sie den Text auf ein Kreis-Steuerelement. Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.

 Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden. Für das Kreis-Steuerelement, überschreiben Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> und <xref:System.Windows.UIElement.OnDragLeave%2A> Methoden. Wenn die Daten gezogen werden, über dem Steuerelement, das die aktuelle Hintergrundfarbe <xref:System.Windows.Shapes.Shape.Fill%2A> wird in einer Platzhaltervariablen gespeichert. Klicken Sie dann die Zeichenfolge in einen Pinsel konvertiert und angewendet werden, um die <xref:System.Windows.Shapes.Ellipse> des Kreises bereitstellt Benutzeroberfläche. Wenn die Daten aus den Kreis gezogen werden, ohne abgelegt zu werden, die ursprüngliche <xref:System.Windows.Shapes.Shape.Fill%2A> Wert erneut auf den Kreis angewendet.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen

1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2.  Deklarieren Sie in der Kreis-Klasse eine Private <xref:System.Windows.Media.Brush> Variable mit dem Namen `_previousFill` und initialisieren Sie es mit `null`.

     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragEnter%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragEnter> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Dies <xref:System.Windows.UIElement.OnDragEnter%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Speichert die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft der <xref:System.Windows.Shapes.Ellipse> in die `_previousFill` Variable.

    -   Führt die gleichen Überprüfungen, die in ausgeführt werden, die <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob die Daten können, um konvertiert werden eine <xref:System.Windows.Media.Brush>.

    -   Wenn die Daten auf eine gültige konvertiert werden <xref:System.Windows.Media.Brush>, wendet sie auf die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse>.

4.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragLeave%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragLeave> Ereignis.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Dies <xref:System.Windows.UIElement.OnDragLeave%2A> -Überschreibung führt die folgenden Aufgaben:

    -   Gilt die <xref:System.Windows.Media.Brush> gespeichert, der `_previousFill` Variable die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , der die Benutzeroberfläche des Kreis-Steuerelements bereitstellt.

5.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

6.  Wählen Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.

7.  Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen. Der Kreis ändert sich von Blau in Grün.

     ![Vorschau der Auswirkungen eines Drag & Drop-Vorgangs](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8.  Ziehen Sie den Text vom Kreis-Steuerelement weg. Der Kreis ändert sich von Grün zurück in Blau.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Konfigurieren eines Panels, abgelegte Daten zu empfangen

In diesem Abschnitt ermöglichen Sie die Bereiche, die als Ziele für gezogene Kreisdaten zu fungieren die Kreis-Steuerelemente hosten. Implementieren Sie Code, der Sie einen Kreis von einem Panel auf einen anderen verschieben oder um eine Kopie eines Kreis-Steuerelements zu machen, indem Sie sie gedrückt halten, ermöglicht die **STRG** gedrückt, während der Drag & Drop eines Kreises.

1.  Öffnen Sie „MainWindow.xaml“.

2.  Siehe das folgende XAML, in den einzelnen der <xref:System.Windows.Controls.StackPanel> -Steuerelemente, Hinzufügen von Ereignishandlern für die <xref:System.Windows.UIElement.DragOver> und <xref:System.Windows.UIElement.Drop> Ereignisse. Name der <xref:System.Windows.UIElement.DragOver> -Ereignishandler `panel_DragOver`, und nennen Sie die <xref:System.Windows.UIElement.Drop> -Ereignishandler `panel_Drop`.

     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3.  Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.

4.  Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.DragOver> -Ereignishandler.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Dies <xref:System.Windows.UIElement.DragOver> -Ereignishandler führt die folgenden Aufgaben:

    -   Überprüft, ob die gezogenen Daten die "Objekt"-Daten enthält, die in gepackt wurde die <xref:System.Windows.DataObject> durch das Kreis-Steuerelement, und übergeben Sie im Aufruf von <xref:System.Windows.DragDrop.DoDragDrop%2A>.

    -   Wenn die "Objekt"-Daten vorhanden ist, überprüft, ob die **STRG** gedrückt wird.

    -   Wenn die **STRG** -Taste gedrückt wird, legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy>. Andernfalls legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Move>.

5.  Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.Drop> -Ereignishandler.

     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Dies <xref:System.Windows.UIElement.Drop> -Ereignishandler führt die folgenden Aufgaben:

    -   Überprüft, ob die <xref:System.Windows.UIElement.Drop> -Ereignis bereits behandelt wurde. Z. B. wenn ein Kreis auf einem anderen gelöscht wird Kreis die Handles der <xref:System.Windows.UIElement.Drop> -Ereignis, Sie möchten nicht im Bereich, der der Kreis zusätzlich behandeln enthält.

    -   Wenn die <xref:System.Windows.UIElement.Drop> -Ereignis nicht behandelt wird, überprüft, ob die **STRG** gedrückt wird.

    -   Wenn die **STRG** gedrückt wird, wenn die <xref:System.Windows.UIElement.Drop> geschieht, wird eine Kopie des Kreises zu steuern, und fügen sie der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.StackPanel>.

    -   Wenn die **STRG** Taste nicht gedrückt wird, verschiebt der Kreis aus der <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung seines übergeordneten Panels, die <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung des Panels, das er abgelegt wurde.

    -   Legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft benachrichtigt die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode gibt an, ob ein Verschiebe- oder Kopiervorgang-Vorgang ausgeführt wurde.

6.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

7.  Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.

8.  Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.

9. Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab. Der Kreis wird entfernt, von der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung im linken Bereich und der Auflistung untergeordneter Elemente des rechten Panels hinzugefügt.

10. Ziehen Sie ein Kreis-Steuerelement aus dem Bereich, es das andere Panel ist, und legen Sie es beim Drücken der **STRG** Schlüssel. Der Kreis wird kopiert und die Kopie wird hinzugefügt, um die <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung des empfangenden Panels.

     ![Ziehen eines Kreises bei gedrückter STRG-Taste](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>Siehe auch

- [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)