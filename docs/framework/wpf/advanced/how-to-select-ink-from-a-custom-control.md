---
title: 'Vorgehensweise: Auswählen von Freihandeingaben aus einem benutzerdefinierten Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 8517041fd9a1864abfb32851314a2926ddab5a3e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363775"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Vorgehensweise: Auswählen von Freihandeingaben aus einem benutzerdefinierten Steuerelement
Durch das Hinzufügen einer <xref:System.Windows.Ink.IncrementalLassoHitTester> für Ihr benutzerdefiniertes Steuerelement, Sie können das Steuerelement, damit Benutzer Freihandeingaben mit einem Lasso-Tool, das ähnlich wie die auswählen kann die <xref:System.Windows.Controls.InkCanvas> Freihandeingaben mit einem Lasso durch.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie mit dem Erstellen eines benutzerdefinierten Steuerelements von Freihandeingaben vertraut sind.  Um ein benutzerdefiniertes Steuerelement erstellen, die Freihandeingabe akzeptiert werden, finden Sie unter [Erstellen eines Freihandeingabesteuerelements](creating-an-ink-input-control.md).  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer mit einem Lasso, zeichnet der <xref:System.Windows.Ink.IncrementalLassoHitTester> vorhersagt, welche Striche innerhalb der Lassopfad Grenzen werden, nachdem der Benutzer das Lasso abgeschlossen hat.  Striche, die sich innerhalb der Lassopfad Grenzen bestimmt werden können ausgewählter betrachtet werden.  Ausgewählten Striche können auch nicht ausgewählt werden.  Wenn der Benutzer Richtung während der Lasso umgekehrt z. B. die <xref:System.Windows.Ink.IncrementalLassoHitTester> möglicherweise einige Striche deaktivieren.  
  
 Die <xref:System.Windows.Ink.IncrementalLassoHitTester> löst die <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> -Ereignis, das das benutzerdefinierte Steuerelement reagiert, während der Benutzer das Lasso ist aktiviert.  Beispielsweise können Sie die Darstellung von Strichen ändern, da der Benutzer auswählt, und Ihre Auswahl wieder aufgehoben.  
  
## <a name="managing-the-ink-mode"></a>Verwalten des Freihandmodus  
 Es ist hilfreich, den Benutzer, wenn das Lasso anders als die Freihandeingaben auf das Steuerelement angezeigt wird. Um dies zu erreichen, das benutzerdefinierte Steuerelement muss von verfolgt, ob der Benutzer schreiben oder auswählen von Freihandeingaben. Die einfachste Möglichkeit hierzu ist, deklarieren Sie eine Enumeration mit zwei Werten: eine, um anzugeben, dass der Benutzer schreibt Freihand- und eine, um anzugeben, dass der Benutzer Freihandeingaben auswählt.  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Als Nächstes fügen Sie zwei <xref:System.Windows.Ink.DrawingAttributes> der Klasse: andere, wenn der Benutzer, zu verwendende Freihandeingaben, wenn der Benutzer die Freihandeingaben auswählt.  Im Konstruktor initialisiert die <xref:System.Windows.Ink.DrawingAttributes> und fügen Sie beide <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> Ereignisse an denselben Ereignishandler. Legen Sie dann die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> Eigenschaft der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> der Freihandeingabe <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Fügen Sie eine Eigenschaft, die den Auswahlmodus verfügbar macht. Festlegen, wenn der Benutzer den Auswahlmodus ändert, die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> Eigenschaft der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> an die entsprechende <xref:System.Windows.Ink.DrawingAttributes> Objekt aus, und fügen Sie dann wieder der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Eigenschaft, um die <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Bereitstellen der <xref:System.Windows.Ink.DrawingAttributes> als Eigenschaften, sodass Anwendungen die Darstellung der letzte Striche und Auswahl von Strichen ermitteln können.  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Wenn eine Eigenschaft des eine <xref:System.Windows.Ink.DrawingAttributes> Objekts ändert, die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> erneut angefügt werden muss, um die <xref:System.Windows.Controls.InkPresenter>.  Im Ereignishandler für die <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> Ereignis Anfügen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> auf die <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Verwenden von IncrementalLassoHitTester  
 Erstellen und initialisieren Sie ein <xref:System.Windows.Ink.StrokeCollection> , die die ausgewählten Striche enthält.  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Wenn der Benutzer beginnt, die einen Strich gezeichnet werden soll, deaktivieren Text- oder Freihandnotizen Lassos, Sie alle ausgewählten Striche. Erstellen Sie Sie dann, wenn der Benutzer eine Lasso ist, eine <xref:System.Windows.Ink.IncrementalLassoHitTester> durch Aufrufen von <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, abonnieren Sie die <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> -Ereignis, und rufen <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Dieser Code kann eine separate Methode und aufgerufen werden aus der <xref:System.Windows.UIElement.OnStylusDown%2A> und <xref:System.Windows.UIElement.OnMouseDown%2A> Methoden.  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Fügen Sie die Tablettstiftpunkte, die <xref:System.Windows.Ink.IncrementalLassoHitTester> während der Benutzer das Lasso zeichnet.  Rufen Sie die folgende Methode aus der <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, und <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> Methoden.  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Behandeln der <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> Ereignis reagieren, wenn der Benutzer auswählt, und hebt die Auswahl Striche.  Die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> -Klasse verfügt über die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> und <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> Eigenschaften, die die Striche, die abgerufen werden ausgewählt und deaktiviert, bzw. wurden.  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Wenn der Benutzer abgeschlossen ist, das Lasso, kündigen die <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> Ereignis, und rufen <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Zusammenfassung aller.  
 Im folgende Beispiel wird ein benutzerdefiniertes Steuerelement, das einen Benutzer zum Auswählen von Freihandeingaben mit einem Lasso ermöglicht.  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [Erstellen eines Freihandeingabesteuerelements](creating-an-ink-input-control.md)
