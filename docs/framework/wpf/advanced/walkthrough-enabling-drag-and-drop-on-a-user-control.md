---
title: 'Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 360b453b2a25b6822485f18cc81cb43e313949eb
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement
In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.  
  
 In dieser exemplarischen Vorgehensweise erstellen Sie eine benutzerdefinierte WPF <xref:System.Windows.Controls.UserControl> , die eine Form "Kreis" darstellt. Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen. Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert. Wenn Sie von einem Kreissteuerelement, ziehen Sie eine <xref:System.Windows.Controls.TextBox>, in eine Zeichenfolgendarstellung der Füllfarbe kopiert die <xref:System.Windows.Controls.TextBox>. Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente enthält und eine <xref:System.Windows.Controls.TextBox> zum Testen der Drag-and-Drop-Funktionalität. Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.  
  
 In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:  
  
-   Erstellen eines benutzerdefinierten Steuerelements.  
  
-   Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.  
  
-   Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.  
  
-   Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio 2010  
  
## <a name="creating-the-application-project"></a>Erstellen des Anwendungsprojekts  
 In diesem Abschnitt erstellen Sie die Anwendungsstruktur, die eine Hauptseite mit zwei Bereiche enthält und eine <xref:System.Windows.Controls.TextBox>.  
  
### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Öffnen Sie „MainWindow.xaml“.  
  
3.  Fügen Sie das folgende Markup zwischen den öffnenden und schließenden <xref:System.Windows.Controls.Grid> Tags.  
  
     Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a>Hinzufügen eines neuen Benutzersteuerelements zum Projekt  
 In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.  
  
### <a name="to-add-a-new-user-control"></a>So fügen Sie ein neues Benutzersteuerelement hinzu  
  
1.  Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.  
  
2.  Ändern Sie im Dialogfeld „Neues Element hinzufügen” den Namen in `Circle.xaml`. Klicken Sie dann auf **Hinzufügen**.  
  
     Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.  
  
3.  Öffnen Sie Circle.xaml.  
  
     Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.  
  
4.  Fügen Sie das folgende Markup in das Stammverzeichnis <xref:System.Windows.Controls.Grid> ein einfache Benutzersteuerelement zu erstellen, die einen blauen Kreis als seine Benutzeroberfläche verfügt.  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
6.  Fügen Sie in C# den folgenden Code nach dem Standardkonstruktor hinzu, um einen Kopierkonstruktor zu erstellen. Fügen Sie in Visual Basic den folgenden Code hinzu, um sowohl einen Standardkonstruktor als auch einen Kopierkonstruktor zu erstellen.  
  
     Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann. Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a>So fügen Sie das Benutzersteuerelement dem Hauptfenster hinzu  
  
1.  Öffnen Sie „MainWindow.xaml“.  
  
2.  Fügen Sie den folgenden XAML-Code dem öffnenden <xref:System.Windows.Window> -Tag, um eine XML-Namespaceverweis auf die aktuelle Anwendung zu erstellen.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  Im ersten <xref:System.Windows.Controls.StackPanel>, fügen Sie den folgenden XAML-Code zum Erstellen von zwei Instanzen des Benutzersteuerelements Kreis im ersten Bereich hinzu.  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a>Implementieren der Ereignisse der Ziehquelle im Benutzersteuerelement  
 In diesem Abschnitt, überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren Sie die Drag-and-Drop-Vorgang.  
  
 Wenn ein Ziehvorgang gestartet wird (eine Maustaste gedrückt wird und die Maus bewegt wird), Verpacken Sie die Daten in übertragen werden eine <xref:System.Windows.DataObject>. In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a>Initiieren eines Drag & Drop-Vorgangs  
  
1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnMouseMove%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.MouseMove> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     Dies <xref:System.Windows.UIElement.OnMouseMove%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.  
  
    -   Pakete die Kreis-Daten in eine <xref:System.Windows.DataObject>. In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.  
  
    -   Ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> Methode, um den Drag & Drop-Vorgang zu initiieren. Übergeben Sie die folgenden drei Parameter für die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode:  
  
        -   `dragSource`: Ein Verweis auf dieses Steuerelement.  
  
        -   `data`– Die <xref:System.Windows.DataObject> im vorherigen Code erstellt.  
  
        -   `allowedEffects`– Die zulässigen Drag-and-Drop-Vorgänge, die sind <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Klicken Sie auf eines der Steuerelemente Kreis, und ziehen Sie es über die Bereiche, die andere Kreis und die <xref:System.Windows.Controls.TextBox>. Beim Ziehen von über die <xref:System.Windows.Controls.TextBox>, ändert sich der Cursor, um einen Verschiebevorgang anzugeben.  
  
5.  Beim Ziehen eines Kreises über die <xref:System.Windows.Controls.TextBox>, drücken Sie die STRG-Taste. Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.  
  
6.  Drag & drop einen Kreis auf dem <xref:System.Windows.Controls.TextBox>. Die Zeichenfolgendarstellung der Füllfarbe für den Kreis angehängt der <xref:System.Windows.Controls.TextBox>.  
  
     ![Zeichenfolgendarstellung der Füllfarbe des Kreises](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")  
  
 Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat. Sie können anpassen, dass das Feedback für den Benutzer durch Behandeln der <xref:System.Windows.UIElement.GiveFeedback> Ereignis und einen anderen Cursor festlegen.  
  
### <a name="to-give-feedback-to-the-user"></a>Feedback an den Benutzer geben  
  
1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnGiveFeedback%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.GiveFeedback> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     Dies <xref:System.Windows.UIElement.OnGiveFeedback%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> , in des Ablageziels festgelegte, Werte <xref:System.Windows.UIElement.DragOver> -Ereignishandler.  
  
    -   Legt einen benutzerdefinierten Cursor auf der Grundlage der <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Wert. Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Ziehen eines Kreises über die Bereiche, die andere Kreis steuert und den <xref:System.Windows.Controls.TextBox>. Beachten Sie, dass der Cursor jetzt die benutzerdefinierte Cursor, die Sie angegeben haben sind, in der <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft setzen.  
  
     ![Drag & Drop mit benutzerdefiniertem Cursor](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")  
  
5.  Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.  
  
6.  Ziehen Sie den Text `green` auf ein Kreis-Steuerelement. Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben. Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a>Implementieren der Ereignisse des Ablageziels im Benutzersteuerelement  
 In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs  
  
1.  Öffnen Sie Circle.xaml.  
  
2.  Im öffnenden <xref:System.Windows.Controls.UserControl> zu kennzeichnen, fügen Sie der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft, und legen Sie es auf `true`.  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 Die <xref:System.Windows.UIElement.OnDrop%2A> Methode wird aufgerufen, wenn die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaftensatz auf `true` und Daten aus der Quelle des Ziehvorgangs werden auf das Benutzersteuerelement Kreis gelöscht. In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.  
  
### <a name="to-process-the-dropped-data"></a>So verarbeiten Sie die abgelegten Daten  
  
1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDrop%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.Drop> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     Dies <xref:System.Windows.UIElement.OnDrop%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Verwendet die <xref:System.Windows.DataObject.GetDataPresent%2A> Methode zum Überprüfen, ob die gezogenen Daten einem String-Objekt enthält.  
  
    -   Verwendet die <xref:System.Windows.DataObject.GetData%2A> Methode, um die Zeichenfolgedaten extrahiert werden, wenn es vorhanden ist.  
  
    -   Verwendet eine <xref:System.Windows.Media.BrushConverter> zu dem Versuch, die Zeichenfolge zum Konvertieren einer <xref:System.Windows.Media.Brush>.  
  
    -   Wenn die Konvertierung erfolgreich ist, gilt den Pinsel, der <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , der die Benutzeroberfläche des Steuerelements Kreis bereitstellt.  
  
    -   Markiert die <xref:System.Windows.UIElement.Drop> Ereignis als behandelt. Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Wählen Sie den Text `green` in der <xref:System.Windows.Controls.TextBox>.  
  
5.  Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab. Der Kreis ändert sich von Blau in Grün.  
  
     ![Konvertieren einer Zeichenfolge in einen Pinsel](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")  
  
6.  Geben Sie den Text `green` in der <xref:System.Windows.Controls.TextBox>.  
  
7.  Wählen Sie den Text `gre` in der <xref:System.Windows.Controls.TextBox>.  
  
8.  Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab. Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.  
  
9. Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement. Der Kreis ändert sich von Blau in Grün. Beachten Sie die angezeigte Cursor, ob abhängt die <xref:System.Windows.Controls.TextBox> oder der Kreis entspricht die Quelle des Ziehvorgangs.  
  
 Festlegen der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft `true` und Verarbeitung der gelöschten Daten ist erforderlich, damit ein Element auf ein Ablageziel sein können. Jedoch um eine bessere benutzererfahrung zu gewährleisten, sollten auch behandelt die <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, und <xref:System.Windows.UIElement.DragOver> Ereignisse. In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.  
  
 Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können. Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen. Behandeln Sie dazu die <xref:System.Windows.UIElement.DragOver> Ereignis, und legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft.  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a>So stellen sie sicher, dass die Datenablage zulässig ist  
  
1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
2.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragOver%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.DragOver> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     Dies <xref:System.Windows.UIElement.OnDragOver%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.  
  
    -   Führt die gleichen Überprüfungen, die innerhalb der <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob das Benutzersteuerelement Kreis die gezogenen Daten verarbeiten kann.  
  
    -   Wenn das Benutzersteuerelement die Daten verarbeiten kann, legt der <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
4.  Wählen Sie den Text `gre` in der <xref:System.Windows.Controls.TextBox>.  
  
5.  Ziehen Sie den Text auf ein Kreis-Steuerelement. Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.  
  
 Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden. Für die Kreis-Benutzersteuerelement, setzen Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> und <xref:System.Windows.UIElement.OnDragLeave%2A> Methoden. Wenn die Daten gezogen wird, über dem Steuerelement, das den aktuellen Hintergrund <xref:System.Windows.Shapes.Shape.Fill%2A> in einer Platzhalter-Variablen gespeichert ist. Klicken Sie dann die Zeichenfolge in einen Pinsel konvertiert und angewendet werden, um die <xref:System.Windows.Shapes.Ellipse> , bietet es sich um des Kreis UI. Wenn die Daten aus dem Kreis gezogen werden, nicht abgelegt wird, wird die ursprüngliche <xref:System.Windows.Shapes.Shape.Fill%2A> Wert wieder auf den Kreis angewendet wird.  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen  
  
1.  Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".  
  
2.  In der Klasse Kreis Deklarieren eines privaten <xref:System.Windows.Media.Brush> Variable mit dem Namen `_previousFill` und initialisieren Sie sie mit `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragEnter%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.DragEnter> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     Dies <xref:System.Windows.UIElement.OnDragEnter%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Speichert die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft von der <xref:System.Windows.Shapes.Ellipse> in die `_previousFill` Variable.  
  
    -   Führt die gleichen Überprüfungen, die in ausgeführt werden die <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob die Daten können, um konvertiert werden eine <xref:System.Windows.Media.Brush>.  
  
    -   Wenn die Daten in eine gültige konvertiert werden <xref:System.Windows.Media.Brush>, wendet ihn auf die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse>.  
  
4.  Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragLeave%2A> überschreiben, um eine Klassenbehandlung für bieten die <xref:System.Windows.UIElement.DragLeave> Ereignis.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     Dies <xref:System.Windows.UIElement.OnDragLeave%2A> Außerkraftsetzung führt die folgenden Aufgaben:  
  
    -   Gilt die <xref:System.Windows.Media.Brush> gespeichert, der `_previousFill` Variable auf die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , der die Benutzeroberfläche des Benutzersteuerelements Kreis bereitstellt.  
  
5.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
6.  Wählen Sie den Text `green` in der <xref:System.Windows.Controls.TextBox>.  
  
7.  Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen. Der Kreis ändert sich von Blau in Grün.  
  
     ![Vorschau der Auswirkungen eines Drag & Drop-Vorgangs](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")  
  
8.  Ziehen Sie den Text vom Kreis-Steuerelement weg. Der Kreis ändert sich von Grün zurück in Blau.  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a>Einem Panel ermöglichen, abgelegte Daten zu empfangen  
 In diesem Abschnitt werden Sie den Panels, die die Kreis-Steuerelemente hosten, ermöglichen, als Ziele für gezogene Kreisdaten zu fungieren. Sie werden Code implementieren, der es Ihnen ermöglicht, einen Kreis von einem Panel in ein anderes zu verschieben, oder eine Kopie eines Kreis-Steuerelements zu erstellen, indem Sie die STRG-Taste gedrückt halten, während Sie einen Kreis ziehen und ablegen.  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a>So konfigurieren Sie das Panel als Ziel eines Ablegevorgangs  
  
1.  Öffnen Sie „MainWindow.xaml“.  
  
2.  Wie in den folgenden XAML-Code in den einzelnen gezeigt die <xref:System.Windows.Controls.StackPanel> Handler für Hinzufügen von Steuerelementen, die <xref:System.Windows.UIElement.DragOver> und <xref:System.Windows.UIElement.Drop> Ereignisse. Name der <xref:System.Windows.UIElement.DragOver> Ereignishandler, d. h. `panel_DragOver`, und nennen Sie die <xref:System.Windows.UIElement.Drop> Ereignishandler, d. h. `panel_Drop`.  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.  
  
4.  Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.DragOver> -Ereignishandler.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Dies <xref:System.Windows.UIElement.DragOver> -Ereignishandler führt die folgenden Aufgaben:  
  
    -   Überprüft, ob die gezogenen Daten die "Object"-Daten enthält, die in gepackt wurde die <xref:System.Windows.DataObject> durch das Benutzersteuerelement Kreis und im Aufruf übergeben <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
    -   Überprüft, ob die STRG-Taste gedrückt wird, falls die „Objekt”-Daten vorhanden sind.  
  
    -   Wenn Sie die STRG-Taste gedrückt wird, legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy>. Andernfalls legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Move>.  
  
5.  Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.Drop> -Ereignishandler.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Dies <xref:System.Windows.UIElement.Drop> -Ereignishandler führt die folgenden Aufgaben:  
  
    -   Überprüft, ob die <xref:System.Windows.UIElement.Drop> Ereignis bereits behandelt wurde. Z. B. wenn ein Kreis, auf einem anderen gelöscht wird Circle der Ziehpunkte die <xref:System.Windows.UIElement.Drop> Ereignis, Sie möchten nicht den Bereich, der den Kreis auch enthält.  
  
    -   Wenn die <xref:System.Windows.UIElement.Drop> Ereignis wird nicht verarbeitet, überprüft, ob die STRG-Taste gedrückt wird.  
  
    -   Wenn Sie die STRG-Taste gedrückt wird, wenn die <xref:System.Windows.UIElement.Drop> erfolgt, erstellt er eine Kopie des Kreises steuern, und fügen Sie diese der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.StackPanel>.  
  
    -   Wenn Sie nicht die STRG-Taste gedrückt wird, verschiebt den Kreis aus der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung des übergeordneten Bereichs in der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung des Bereichs, die sie gelöscht wurde, auf.  
  
    -   Legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft benachrichtigt die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode, ob ein Verschiebe- oder Kopiervorgang-Vorgang ausgeführt wurde.  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
7.  Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.  
  
8.  Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.  
  
9. Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab. Der Kreis wird daraus der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung im linken Bereich und auf die Auflistung der untergeordneten Elemente des rechten Bereichs hinzugefügt.  
  
10. Ziehen Sie ein Kreis-Steuerelement aus dem Panel, in dem es sich befindet, in das andere Panel und legen Sie es bei gedrückter STRG-Taste ab. Der Kreis wird kopiert und die Kopie wird hinzugefügt, um die <xref:System.Windows.Controls.Panel.Children%2A> Auflistung der Bereiche "empfangen".  
  
     ![Ziehen eines Kreises bei gedrückter STRG-Taste](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Drag & Drop](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
