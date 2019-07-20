---
title: 'Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 80fd55be9230729cb8336be91c1d8fb4f7f3f080
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364263"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement

In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.

In dieser exemplarischen Vorgehensweise erstellen Sie ein benutzerdefiniertes <xref:System.Windows.Controls.UserControl> WPF, das eine Kreisform darstellt. Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen. Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert. Wenn Sie von einem Kreis-Steuerelement zu <xref:System.Windows.Controls.TextBox>einem ziehen, wird die Zeichen folgen Darstellung der Füllfarbe in <xref:System.Windows.Controls.TextBox>den kopiert. Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente und <xref:System.Windows.Controls.TextBox> ein-Element enthält, um die Drag & amp; Drop-Funktionalität zu testen. Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.

In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:

- Erstellen eines benutzerdefinierten Steuerelements.

- Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.

- Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.

- Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-application-project"></a>Erstellen des Anwendungs Projekts
 In diesem Abschnitt erstellen Sie die Anwendungs Infrastruktur, die eine Hauptseite mit zwei Panels und <xref:System.Windows.Controls.TextBox>enthält.

1. Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung.

2. Öffnen Sie „MainWindow.xaml“.

3. Fügen Sie das folgende Markup zwischen den öffnenden <xref:System.Windows.Controls.Grid> und schließenden Tags hinzu.

     Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Hinzufügen eines neuen Benutzer Steuer Elements zum Projekt
 In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.

1. Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.

2. Ändern Sie im Dialogfeld **Neues Element hinzufügen** den Namen `Circle.xaml`in, und klicken Sie auf **Hinzufügen**.

     Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.

3. Öffnen Sie Circle.xaml.

     Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.

4. Fügen Sie dem Stamm das folgende Markup <xref:System.Windows.Controls.Grid> hinzu, um ein einfaches Benutzer Steuerelement mit einem blauen Kreis als Benutzeroberfläche zu erstellen.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

6. Fügen C#Sie in den folgenden Code nach dem Parameter losen Konstruktor hinzu, um einen Kopierkonstruktor zu erstellen. Fügen Sie in Visual Basic den folgenden Code hinzu, um einen Parameter losen Konstruktor und einen Kopierkonstruktor zu erstellen.

     Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann. Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Hinzufügen des Benutzer Steuer Elements zum Hauptfenster

1. Öffnen Sie „MainWindow.xaml“.

2. Fügen Sie dem öffnenden <xref:System.Windows.Window> Tag den folgenden XAML-Code hinzu, um einen XML-Namespace Verweis auf die aktuelle Anwendung zu erstellen.

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. Fügen Sie im <xref:System.Windows.Controls.StackPanel>ersten-Element den folgenden XAML-Code hinzu, um zwei Instanzen des Kreis-Benutzer Steuer Elements im ersten Panel zu erstellen.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Implementieren von Drag Source-Ereignissen im Benutzer Steuerelement
 In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren den Drag & Drop-Vorgang.

 Wenn ein Drag-Vorgang gestartet wird (eine Maustaste gedrückt wird und die Maus bewegt wird), Verpacken Sie die Daten, die in eine <xref:System.Windows.DataObject>übertragen werden sollen. In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Initiieren eines Drag & Drop-Vorgangs

1. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2. Fügen Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.MouseMove> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Diese <xref:System.Windows.UIElement.OnMouseMove%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.

    - Verpackt die Zirkel Daten in <xref:System.Windows.DataObject>eine. In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.

    - Ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> -Methode auf, um den Drag & Drop-Vorgang zu initiieren. Sie übergeben die folgenden drei Parameter an die <xref:System.Windows.DragDrop.DoDragDrop%2A> -Methode:

        - `dragSource`: Ein Verweis auf dieses Steuerelement.

        - `data`– Die <xref:System.Windows.DataObject> , die im vorherigen Code erstellt wurde.

        - `allowedEffects`– Die zulässigen Drag & Drop-Vorgänge, die oder <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move>sind.

3. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4. Klicken Sie auf eines der Kreis-Steuerelemente, und ziehen Sie es über die Bereiche, den <xref:System.Windows.Controls.TextBox>anderen Kreis und. Beim ziehen über das <xref:System.Windows.Controls.TextBox>wird der Cursor geändert, um eine Verschiebung anzugeben.

5. Drücken Sie beim Ziehen eines Kreises <xref:System.Windows.Controls.TextBox>über die **STRG** -Taste. Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.

6. Ziehen Sie einen Kreis mit Drag und <xref:System.Windows.Controls.TextBox>Drop auf die. Die Zeichen folgen Darstellung der Füllfarbe des Kreises wird an den <xref:System.Windows.Controls.TextBox>angefügt.

     ![Zeichenfolgendarstellung der Füllfarbe des Kreises](./media/dragdrop-colorstring.png "DragDrop_ColorString")

Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat. Sie können das Feedback an den Benutzer anpassen, indem Sie das <xref:System.Windows.UIElement.GiveFeedback> -Ereignis behandeln und einen anderen Cursor festlegen.

## <a name="give-feedback-to-the-user"></a>Feedback an den Benutzer senden

1. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2. Fügen Sie die <xref:System.Windows.UIElement.OnGiveFeedback%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.GiveFeedback> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Diese <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Werte, die im-Ereignishandler des Drop <xref:System.Windows.UIElement.DragOver> -Ziels festgelegt sind.

    - Legt einen benutzerdefinierten Cursor basierend auf <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> dem-Wert fest. Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.

3. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4. Ziehen Sie eines der Kreis-Steuerelemente auf die Bereiche, den anderen Kreis und <xref:System.Windows.Controls.TextBox>. Beachten Sie, dass die Cursor jetzt die benutzerdefinierten Cursor sind, die <xref:System.Windows.UIElement.OnGiveFeedback%2A> Sie in der Überschreibung angegeben haben.

     ![Drag & Drop mit benutzerdefiniertem Cursor](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5. Wählen Sie den `green` Text aus <xref:System.Windows.Controls.TextBox>der aus.

6. Ziehen Sie den Text `green` auf ein Kreis-Steuerelement. Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben. Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.

## <a name="implement-drop-target-events-in-the-user-control"></a>Implementieren von Drop Target-Ereignissen im Benutzer Steuerelement
 In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs

1. Öffnen Sie Circle.xaml.

2. Fügen Sie im <xref:System.Windows.Controls.UserControl> öffnenden Tag die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaft hinzu, und `true`legen Sie Sie auf fest.

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

Die <xref:System.Windows.UIElement.OnDrop%2A> -Methode wird aufgerufen, <xref:System.Windows.UIElement.AllowDrop%2A> wenn die-Eigenschaft `true` auf festgelegt ist und Daten aus der Zieh Quelle im Kreis-Benutzer Steuerelement abgelegt werden. In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.

### <a name="to-process-the-dropped-data"></a>So verarbeiten Sie die abgelegten Daten

1. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2. Fügen Sie die <xref:System.Windows.UIElement.OnDrop%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.Drop> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Diese <xref:System.Windows.UIElement.OnDrop%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Verwendet die <xref:System.Windows.DataObject.GetDataPresent%2A> -Methode, um zu überprüfen, ob die gezogenen Daten ein Zeichen folgen Objekt enthalten.

    - Verwendet die <xref:System.Windows.DataObject.GetData%2A> -Methode, um die Zeichen folgen Daten zu extrahieren, sofern diese vorhanden sind.

    - Verwendet einen <xref:System.Windows.Media.BrushConverter> , um zu versuchen, die Zeichenfolge <xref:System.Windows.Media.Brush>in eine zu konvertieren.

    - Wenn die Konvertierung erfolgreich ist, wendet den Pinsel auf den <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> des an, der die Benutzeroberfläche des Kreis-Steuer Elements bereitstellt.

    - Markiert das <xref:System.Windows.UIElement.Drop> Ereignis als behandelt. Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.

3. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4. Wählen Sie den `green` Text <xref:System.Windows.Controls.TextBox>in aus.

5. Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab. Der Kreis ändert sich von Blau in Grün.

     ![Konvertieren einer Zeichenfolge in einen Pinsel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6. Geben Sie den `green` Text in <xref:System.Windows.Controls.TextBox>der ein.

7. Wählen Sie den `gre` Text <xref:System.Windows.Controls.TextBox>in aus.

8. Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab. Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.

9. Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement. Der Kreis ändert sich von Blau in Grün. Beachten Sie, dass der angezeigte Cursor davon abhängt <xref:System.Windows.Controls.TextBox> , ob der oder der Kreis die Zieh Quelle ist.

Das Festlegen <xref:System.Windows.UIElement.AllowDrop%2A> der- `true` Eigenschaft auf und die Verarbeitung der gelöschten Daten ist alles, was erforderlich ist, um ein Element als Ablage Ziel zu aktivieren. Um jedoch eine bessere Benutzer Leistung zu gewährleisten, sollten Sie auch die <xref:System.Windows.UIElement.DragEnter>Ereignisse <xref:System.Windows.UIElement.DragLeave>, und <xref:System.Windows.UIElement.DragOver> behandeln. In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.

Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können. Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen. Zu diesem Zweck behandeln Sie das <xref:System.Windows.UIElement.DragOver> -Ereignis und legen die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft fest.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>So stellen sie sicher, dass die Datenablage zulässig ist

1. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2. Fügen Sie die <xref:System.Windows.UIElement.OnDragOver%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragOver> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Diese <xref:System.Windows.UIElement.OnDragOver%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.

    - Führt die gleichen Überprüfungen durch, die in <xref:System.Windows.UIElement.OnDrop%2A> der-Methode ausgeführt werden, um zu bestimmen, ob das Kreis-Benutzer Steuerelement die gezogenen Daten verarbeiten kann.

    - Wenn das Benutzer Steuerelement die Daten verarbeiten kann, wird <xref:System.Windows.DragEventArgs.Effects%2A> die- <xref:System.Windows.DragDropEffects.Copy> Eigenschaft <xref:System.Windows.DragDropEffects.Move>auf oder festgelegt.

3. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

4. Wählen Sie den `gre` Text <xref:System.Windows.Controls.TextBox>in aus.

5. Ziehen Sie den Text auf ein Kreis-Steuerelement. Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.

 Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden. Für das Kreis-Benutzer Steuerelement überschreiben Sie <xref:System.Windows.UIElement.OnDragEnter%2A> die <xref:System.Windows.UIElement.OnDragLeave%2A> -Methode und die-Methode. Wenn die Daten über das Steuerelement gezogen werden, wird der <xref:System.Windows.Shapes.Shape.Fill%2A> aktuelle Hintergrund in einer Platzhalter Variablen gespeichert. Die Zeichenfolge wird dann in einen Pinsel konvertiert und auf das <xref:System.Windows.Shapes.Ellipse> angewendet, das die Benutzeroberfläche des Kreises bereitstellt. Wenn die Daten aus dem Kreis gezogen werden, ohne gelöscht zu werden, wird <xref:System.Windows.Shapes.Shape.Fill%2A> der ursprüngliche Wert erneut auf den Kreis angewendet.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen

1. Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".

2. Deklarieren Sie in der Klasse Circle eine <xref:System.Windows.Media.Brush> private Variable `_previousFill` mit dem Namen, und `null`Initialisieren Sie Sie mit.

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. Fügen Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragEnter> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Diese <xref:System.Windows.UIElement.OnDragEnter%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Speichert die <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft <xref:System.Windows.Shapes.Ellipse> des in der `_previousFill` Variablen.

    - Führt die gleichen Überprüfungen durch, die in <xref:System.Windows.UIElement.OnDrop%2A> der-Methode ausgeführt werden, um zu bestimmen, ob <xref:System.Windows.Media.Brush>die Daten in einen konvertiert werden können.

    - Wenn die Daten in einen gültigen <xref:System.Windows.Media.Brush>konvertiert werden, wendet ihn auf den <xref:System.Windows.Shapes.Shape.Fill%2A> von <xref:System.Windows.Shapes.Ellipse>an.

4. Fügen Sie die <xref:System.Windows.UIElement.OnDragLeave%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragLeave> Klassen Behandlung für das-Ereignis bereitzustellen

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Diese <xref:System.Windows.UIElement.OnDragLeave%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:

    - Wendet das <xref:System.Windows.Media.Brush> ,dasinder<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Shape.Fill%2A> `_previousFill` Variablen gespeichert ist, auf die des an, das die Benutzeroberfläche des Kreis-Benutzer Steuer Elements bereitstellt.

5. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

6. Wählen Sie den `green` Text <xref:System.Windows.Controls.TextBox>in aus.

7. Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen. Der Kreis ändert sich von Blau in Grün.

     ![Vorschau der Auswirkungen eines Drag & Drop-Vorgangs](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8. Ziehen Sie den Text vom Kreis-Steuerelement weg. Der Kreis ändert sich von Grün zurück in Blau.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Aktivieren eines Panels zum Empfangen von gelöschten Daten

In diesem Abschnitt ermöglichen Sie den Bereichen, die die Kreis-Benutzer Steuerelemente hosten, als Dropziele für gezogene Kreis Daten zu fungieren. Sie implementieren Code, der es Ihnen ermöglicht, einen Kreis von einem Bereich in einen anderen zu verschieben oder eine Kopie eines Kreis-Steuer Elements zu erstellen, indem Sie die **STRG** -Taste gedrückt halten, während Sie einen Kreis ziehen und ablegen.

1. Öffnen Sie „MainWindow.xaml“.

2. Fügen Sie, wie im folgenden XAML-Code gezeigt, <xref:System.Windows.Controls.StackPanel> Handler für das-Ereignis und das <xref:System.Windows.UIElement.DragOver> - <xref:System.Windows.UIElement.Drop> Ereignis hinzu. Benennen Sie <xref:System.Windows.UIElement.DragOver> den Ereignishandler `panel_DragOver`,, und `panel_Drop`benennen <xref:System.Windows.UIElement.Drop> Sie den Ereignishandler.

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.

4. Fügen Sie den folgenden Code für <xref:System.Windows.UIElement.DragOver> den-Ereignishandler hinzu.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Dieser <xref:System.Windows.UIElement.DragOver> Ereignishandler führt die folgenden Aufgaben aus:

    - Überprüft, ob die gezogenen Daten die "Objekt"-Daten enthalten, die vom <xref:System.Windows.DataObject> Kreis-Benutzer Steuerelement in den gepackt und in den <xref:System.Windows.DragDrop.DoDragDrop%2A>-Befehl übermittelt wurden.

    - Wenn die "Objekt"-Daten vorhanden sind, wird überprüft, ob die **STRG** -Taste gedrückt wird.

    - Wenn die **STRG** -Taste gedrückt wird, wird <xref:System.Windows.DragEventArgs.Effects%2A> die- <xref:System.Windows.DragDropEffects.Copy>Eigenschaft auf festgelegt. Legen Sie andernfalls die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft <xref:System.Windows.DragDropEffects.Move>auf fest.

5. Fügen Sie den folgenden Code für <xref:System.Windows.UIElement.Drop> den-Ereignishandler hinzu.

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Dieser <xref:System.Windows.UIElement.Drop> Ereignishandler führt die folgenden Aufgaben aus:

    - Überprüft, ob <xref:System.Windows.UIElement.Drop> das Ereignis bereits behandelt wurde. Wenn beispielsweise ein Kreis in einem anderen Kreis abgelegt wird, der das <xref:System.Windows.UIElement.Drop> -Ereignis behandelt, soll der Bereich, der den Kreis enthält, nicht ebenfalls behandelt werden.

    - Wenn das <xref:System.Windows.UIElement.Drop> Ereignis nicht behandelt wird, überprüft, ob die **STRG** -Taste gedrückt ist.

    - Wenn beim Auftreten der **STRG** -Taste gedrückt <xref:System.Windows.UIElement.Drop> wird, erstellt eine Kopie des Kreis-Steuer Elements und fügt es <xref:System.Windows.Controls.StackPanel>der <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung von hinzu.

    - Wenn die **STRG** -Taste nicht gedrückt wird, verschiebt den Kreis aus <xref:System.Windows.Controls.Panel.Children%2A> der-Auflistung des übergeordneten Bereichs <xref:System.Windows.Controls.Panel.Children%2A> in die-Auflistung des Panels, in dem Sie abgelegt wurde.

    - Legt die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft fest, <xref:System.Windows.DragDrop.DoDragDrop%2A> um die Methode zu benachrichtigen, ob ein verschiebe-oder Kopiervorgang ausgeführt wurde.

6. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.

7. Wählen Sie den `green` Text aus <xref:System.Windows.Controls.TextBox>der aus.

8. Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.

9. Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab. Der Kreis wird aus der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung des linken Bereichs entfernt und der Auflistung Children des rechten Panels hinzugefügt.

10. Ziehen Sie ein Kreis-Steuerelement aus dem Bereich in den anderen Bereich, und legen Sie es beim Drücken der **STRG** -Taste ab. Der Kreis wird kopiert, <xref:System.Windows.Controls.Panel.Children%2A> und die Kopie wird der Auflistung des Empfangsbereichs hinzugefügt.

     ![Ziehen eines Kreises bei gedrückter STRG-Taste](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>Siehe auch

- [Übersicht über Drag & Drop](drag-and-drop-overview.md)
