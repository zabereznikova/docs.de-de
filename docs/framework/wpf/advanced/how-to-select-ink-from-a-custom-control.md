---
title: "Gewusst wie: Ausw&#228;hlen von Freihandeingaben aus einem benutzerdefinierten Steuerelement | Microsoft Docs"
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
  - "Steuerelemente, Freihandeingabenauswahl"
  - "Benutzerdefinierte Steuerelemente, Freihandeingabenauswahl"
  - "Freihandeingaben, Auswählen aus einem benutzerdefinierten Steuerelement"
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Ausw&#228;hlen von Freihandeingaben aus einem benutzerdefinierten Steuerelement
Durch Hinzufügen eines <xref:System.Windows.Ink.IncrementalLassoHitTester> zu einem benutzerdefinierten Steuerelement können Sie ermöglichen, dass ein Benutzer Freihandeingaben mit einem Lassowerkzeug auswählen kann, ähnlich wie das Auswählen von Freihandeingaben mit einem Lasso bei <xref:System.Windows.Controls.InkCanvas>.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie mit dem Erstellen eines benutzerdefinierten Steuerelements für Freihandeingaben vertraut sind.  Informationen zum Erstellen eines benutzerdefinierten Steuerelements, das Freihandeingabe akzeptiert, finden Sie unter [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
## Beispiel  
 Beim Ziehen eines Lassos durch den Benutzer berechnet der <xref:System.Windows.Ink.IncrementalLassoHitTester>, welche Striche sich nach der Fertigstellung des Lassos innerhalb des Lassobereiches befinden werden.  Striche, die sich innerhalb des Lassobereiches befinden, gelten dabei als ausgewählt.  Die Auswahl von ausgewählten Strichen kann auch wieder aufgehoben werden.  Wenn der Benutzer zum Beispiel die Richtung umkehrt, während er das Lasso zieht, kann der <xref:System.Windows.Ink.IncrementalLassoHitTester> die Auswahl von Strichen wieder aufheben.  
  
 Der <xref:System.Windows.Ink.IncrementalLassoHitTester> löst das <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>\-Ereignis aus, sodass ein benutzerdefiniertes Steuerelement reagieren kann, während der Benutzer das Lasso zieht.  So können Sie zum Beispiel die Darstellung von Strichen ändern, wenn sie vom Benutzer ausgewählt werden oder ihre Auswahl wieder aufgehoben wird.  
  
## Verwalten des Freihandmodus  
 Es ist für den Benutzer hilfreich, wenn das Lasso anders angezeigt wird, als die Freihandeingabe im Steuerelement.  Dazu muss das benutzerdefinierte Steuerelement verfolgen, ob der Benutzer Freihandeingaben durchführt oder auswählt.  Am einfachsten lässt sich dies erreichen, indem man eine Enumeration mit zwei Werten deklariert: Ein Wert zum Anzeigen, dass der Benutzer Freihandeingaben durchführt, und der andere Wert zum Anzeigen, dass der Benutzer Freihandeingaben auswählt.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Anschließend fügen Sie der Klasse zwei <xref:System.Windows.Ink.DrawingAttributes> hinzu: Eins, das verwendet werden soll, wenn der Benutzer Freihandeingaben durchführt, und das andere, wenn der Benutzer Freihandeingaben auswählt.  Initialisieren Sie im Konstruktor die <xref:System.Windows.Ink.DrawingAttributes>, und weisen Sie beide <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>\-Ereignisse demselben Ereignishandler zu.  Legen Sie dann für die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>\-Eigenschaft von <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> die Freihandeingabe\-<xref:System.Windows.Ink.DrawingAttributes> fest.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Fügen Sie eine Eigenschaft hinzu, die den Auswahlmodus verfügbar macht.  Wenn der Benutzer den Auswahlmodus ändert, legen Sie für die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>\-Eigenschaft des <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> das entsprechende <xref:System.Windows.Ink.DrawingAttributes>\-Objekt fest, und fügen Sie dann die <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>\-Eigenschaft wieder dem <xref:System.Windows.Controls.InkPresenter> hinzu.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Machen Sie die <xref:System.Windows.Ink.DrawingAttributes> als Eigenschaften verfügbar, sodass Anwendungen die Darstellung von Freihandstrichen und Auswahlstrichen bestimmen können.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Wenn sich eine Eigenschaft eines <xref:System.Windows.Ink.DrawingAttributes>\-Objekts ändert, muss der <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> dem <xref:System.Windows.Controls.InkPresenter> neu zugewiesen werden.  Weisen Sie im Ereignishandler für das <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>\-Ereignis den <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> erneut dem <xref:System.Windows.Controls.InkPresenter> zu.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## Verwenden von IncrementalLassoHitTester  
 Erstellen und initialisieren Sie eine <xref:System.Windows.Ink.StrokeCollection>, die die ausgewählten Striche enthält.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Wenn der Benutzer beginnt, per Freihandeingabe oder per Lasso einen Strich zu ziehen, heben Sie die Auswahl aller aktuell ausgewählten Striche auf.  Erstellen Sie dann – wenn der Benutzer ein Lasso zieht – einen <xref:System.Windows.Ink.IncrementalLassoHitTester> durch Aufrufen von <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, abonnieren Sie das <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>\-Ereignis, und rufen Sie <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A> auf.  Dieser Code kann eine separate Methode sein und von der <xref:System.Windows.UIElement.OnStylusDown%2A>\-Methode und der <xref:System.Windows.UIElement.OnMouseDown%2A>\-Methode aufgerufen werden.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Fügen Sie die Tablettstiftpunkte zum <xref:System.Windows.Ink.IncrementalLassoHitTester> hinzu, während der Benutzer das Lasso zieht.  Rufen Sie die folgende Methode aus den Methoden <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A> und <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> auf.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Verarbeiten Sie das <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=fullName>\-Ereignis als Reaktion, wenn der Benutzer Striche auswählt oder deren Auswahl wieder aufhebt.  Die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs>\-Klasse verfügt über die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A>\-Eigenschaft und die <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A>\-Eigenschaft, die die Striche enthalten, die ausgewählt wurden bzw. deren Auswahl wieder aufgehoben wurde.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Wenn der Benutzer das Ziehen des Lasso beendet, kündigen Sie das Abonnement vom <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>\-Ereignis, und rufen Sie <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A> auf.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## Die Komponenten im Zusammenhang  
 Das folgende Beispiel zeigt ein benutzerdefiniertes Steuerelement, mit dem ein Benutzer Freihandeingaben mit einem Lasso auswählen kann.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>   
 <xref:System.Windows.Ink.StrokeCollection>   
 <xref:System.Windows.Input.StylusPointCollection>   
 [Erstellen eines Freihandeingabesteuerelements](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)