---
title: "Gewusst wie: Formatieren von &quot;UIElement&quot; als transparent oder halbtransparent | Microsoft Docs"
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
  - "Durchlässigkeit, von UIElements"
  - "Transparenz von UIElements"
  - "UIElements, Durchlässigkeit"
  - "UIElements, Transparenz"
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Formatieren von &quot;UIElement&quot; als transparent oder halbtransparent
Dieses Beispiel zeigt, wie Sie ein <xref:System.Windows.UIElement> transparent oder halbtransparent formatieren.  Um dies für ein Element durchzuführen, legen Sie seine <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft fest.  Bei einem Wert von `0.0` ist das Element vollständig transparent, und bei einem Wert von `1.0` ist das Element vollständig undurchsichtig.  Ein Wert von `0.5` bewirkt, dass das Element halbtransparent ist \(usw.\).  Die <xref:System.Windows.UIElement.Opacity%2A> eines Elements ist standardmäßig auf `1.0` gesetzt.  
  
## Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Opacity%2A> einer Schaltfläche auf `0.25` gesetzt, so dass die Schaltfläche und ihr Inhalt \(in diesem Fall der Text der Schaltfläche\) mit 25 % Deckung angezeigt wird.  
  
 [!code-xml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Wenn der Inhalt eines Elements über eigene <xref:System.Windows.UIElement.Opacity%2A>\-Einstellungen verfügt, werden diese Werte mit den <xref:System.Windows.UIElement.Opacity%2A>\-Werten des enthaltenden Elements multipliziert.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.UIElement.Opacity%2A> einer Schaltfläche auf `0.25` gesetzt, und die <xref:System.Windows.UIElement.Opacity%2A> eines <xref:System.Windows.Controls.Image>\-Steuerelements, das Teil der Schaltfläche ist, wird auf `0.5` gesetzt.  Dies führt zu dem Ergebnis, dass das Bild 12,5 % gedeckt angezeigt wird: 0,25 \* 0,5 \= 0,125.  
  
 [!code-xml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Eine andere Möglichkeit, den Durchlässigkeitsgrad eines Elements festzulegen, besteht darin, die Durchlässigkeit des <xref:System.Windows.Media.Brush> festzulegen, mit dem das Element gezeichnet wird.  Bei diesem Ansatz können Sie die Durchlässigkeit von Teilen eines Elements selektiv anpassen, und der Ansatz bietet außerdem Leistungsvorteile im Gegensatz zur Verwendung der <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft eines Elements.  Im folgenden Beispiel wird die <xref:System.Windows.Media.Brush.Opacity%2A> eines <xref:System.Windows.Media.SolidColorBrush>, der zum Zeichnen des <xref:System.Windows.Controls.Control.Background%2A>\-Elements der Schaltfläche verwendet wird, auf `0.25` gesetzt.  Der Hintergrund des Pinsels ist dann zu 25 % deckend, aber der Inhalt \(der Text der Schaltfläche\) ist zu 100 % deckend.  
  
 [!code-xml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 Außerdem können Sie die Durchlässigkeit einzelner Farben innerhalb eines Pinsels steuern.  Weitere Informationen zu Farben und Pinseln finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Ein Beispiel dafür, wie Sie die Durchlässigkeit eines Elements animieren, finden Sie unter [Animieren der Durchlässigkeit eines Elements oder eines Pinsels](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).