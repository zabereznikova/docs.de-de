---
title: "Gewusst wie: Auswählen von Freihandeingaben aus einem benutzerdefinierten Steuerelement"
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
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd9693209cc35ecd3c0473133b7c21639a239ff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Gewusst wie: Auswählen von Freihandeingaben aus einem benutzerdefinierten Steuerelement
Durch Hinzufügen einer <xref:System.Windows.Ink.IncrementalLassoHitTester> an das benutzerdefinierte Steuerelement können Sie das Steuerelement aktivieren, damit ein Benutzer mit einem Lassowerkzeug, ähnlich wie die auswählen kann die <xref:System.Windows.Controls.InkCanvas> Freihandeingaben mit einem Lasso wählt.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie mit Erstellen eines benutzerdefinierten Steuerelements in Freihandeingaben vertraut sind.  Um ein benutzerdefiniertes Steuerelement zu erstellen, das Freihandeingaben akzeptiert, finden Sie unter [Erstellen eines Eingabesteuerelements Freihand-](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## <a name="example"></a>Beispiel  
 Wenn der Benutzer ein Lasso zeichnet die <xref:System.Windows.Ink.IncrementalLassoHitTester> vorhersagt, welche Striche innerhalb der Lassobereiches werden, nachdem der Benutzer das Lasso abgeschlossen hat.  Striche, die innerhalb der Lassobereiches bestimmt werden können als ausgewählt betrachtet werden.  Ausgewählten Striche können auch wieder aufgehoben werden.  Wenn der Benutzer während der Lasso Richtung kehrt z. B. die <xref:System.Windows.Ink.IncrementalLassoHitTester> möglicherweise einige Striche deaktivieren.  
  
 Die <xref:System.Windows.Ink.IncrementalLassoHitTester> löst die <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> Ereignis, das Ihr benutzerdefinierte Steuerelement reagieren, während der Benutzer das Lasso ist aktiviert.  Beispielsweise können Sie die Darstellung der Striche ändern, wie der Benutzer wählt und Ihre Auswahl wieder aufgehoben.  
  
## <a name="managing-the-ink-mode"></a>Verwalten des Freihandmodus  
 Es ist für den Benutzer hilfreich, wenn das Lasso anders als die Freihandeingabe im Steuerelement angezeigt wird. Um dies zu erreichen, das benutzerdefinierte Steuerelement muss Nachverfolgen von, ob der Benutzer schreibt oder Freihand auswählen. Die einfachste Möglichkeit hierzu ist, deklariert eine Enumeration mit zwei Werten: eine, um anzugeben, dass der Benutzer schreibt Freihand- und einen, um anzugeben, dass der Benutzer Freihandeingaben auswählt.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Als Nächstes fügen Sie zwei <xref:System.Windows.Ink.DrawingAttributes> der Klasse: soll, wenn der Benutzer, soll Freihandeingaben, wenn der Benutzer Freihandeingaben auswählt.  Im Konstruktor initialisiert die <xref:System.Windows.Ink.DrawingAttributes> , und fügen Sie beide <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> Ereignisse an den gleichen Ereignishandler. Legen Sie dann die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> Eigenschaft von der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die Ink <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Fügen Sie eine Eigenschaft, die den Auswahlmodus verfügbar macht. Festgelegt, wenn der Benutzer den Auswahlmodus ändert, die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> Eigenschaft von der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> an die entsprechende <xref:System.Windows.Ink.DrawingAttributes> Objekt, und verbinden Sie dann erneut die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Eigenschaft, um die <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Verfügbarmachen der <xref:System.Windows.Ink.DrawingAttributes> als Eigenschaften, sodass Anwendungen die Darstellung der Freihandstriche und der Auswahl Striche ermitteln können.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Wenn eine Eigenschaft einer <xref:System.Windows.Ink.DrawingAttributes> Objekts ändert, die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> erneut angefügt werden muss, um die <xref:System.Windows.Controls.InkPresenter>.  Im Ereignishandler für die <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> Ereignis Anfügen der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> auf die <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Verwenden von IncrementalLassoHitTester  
 Erstellen und initialisieren Sie ein <xref:System.Windows.Ink.StrokeCollection> , das die ausgewählten Striche enthält.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Wenn der Benutzer beginnt, einen Strich gezeichnet werden soll, deaktivieren Sie Freihand- oder Lasso ausgewählten Striche. Erstellen Sie Sie dann, wenn der Benutzer ein Lasso ist ein <xref:System.Windows.Ink.IncrementalLassoHitTester> durch Aufrufen von <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, abonnieren Sie die <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> Ereignis, und rufen <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Dieser Code kann eine separate Methode und aufgerufen werden aus der <xref:System.Windows.UIElement.OnStylusDown%2A> und <xref:System.Windows.UIElement.OnMouseDown%2A> Methoden.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Hinzufügen der Tablettstift verweist auf die <xref:System.Windows.Ink.IncrementalLassoHitTester> während der Benutzer das Lasso zieht.  Rufen Sie die folgende Methode aus der <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, und <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> Methoden.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Behandeln der <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> Ereignis reagiert, wenn der Benutzer wählt aus, und hebt die Auswahl Striche.  Die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> -Klasse verfügt über die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> und <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> Eigenschaften, die die Striche abgerufen werden, die ausgewählt wurden, und bzw.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Wenn der Benutzer das Lasso hat, kündigen von Ereignisabonnements der <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> Ereignis, und rufen <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Platzieren sie alle zusammen.  
 Im folgende Beispiel wird ein benutzerdefiniertes Steuerelement, mit der einen Benutzer mit einem Lasso auswählen kann.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
