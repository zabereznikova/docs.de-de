---
title: "Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pinsel, Zeichnen mit Volltonfarben"
  - "Zeichnen, Mit Volltonfarben"
  - "Volltonfarben, Zeichnen mit"
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Zeichnen eines Bereichs mit einer Volltonfarbe
Zum Zeichnen eines Bereichs mit einer Volltonfarbe können Sie einen vordefinierten Systempinsel verwenden, wie z. B. <xref:System.Windows.Media.Brushes.Red%2A> oder <xref:System.Windows.Media.Brushes.Blue%2A>. Sie haben aber auch die Möglichkeit, einen neuen <xref:System.Windows.Media.SolidColorBrush> zu erstellen und die <xref:System.Windows.Media.SolidColorBrush.Color%2A> mit den ARGB\-Werten \(Alpha, rot, grün und blau\) anzugeben.  In XAML können Sie einen Bereich mit einer Volltonfarbe auch mit der Hexadezimalschreibweise zeichnen.  
  
 In den folgenden Beispielen werden die einzelnen beschriebenen Techniken zum Füllen eines <xref:System.Windows.Shapes.Rectangle> mit blauer Farbe verwendet.  
  
## Beispiel  
 **Verwenden eines vordefinierten Pinsels**  
  
 Im folgenden Beispiel wird der vordefinierte Pinsel <xref:System.Windows.Media.Brushes.Blue%2A> verwendet.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Verwenden einer Hexadezimalnotation**  
  
 Im nächsten Beispiel wird die Hexadezimalschreibweise mit acht Ziffern verwendet.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Verwenden von ARGB\-Werten**  
  
 Im nächsten Beispiel wird ein <xref:System.Windows.Media.SolidColorBrush> erstellt, dessen <xref:System.Windows.Media.SolidColorBrush.Color%2A> mithilfe der ARGB\-Werte für die Farbe Blau definiert wird.  
  
 [!code-xml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Andere Methoden zur Farbdefinition finden Sie im Abschnitt zur <xref:System.Windows.Media.Color>\-Struktur.  
  
 **Verwandte Themen**  
  
 Weitere Informationen zu <xref:System.Windows.Media.SolidColorBrush> und zusätzliche Beispiele finden Sie unter [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
 Dieses Codebeispiel ist Teil eines umfangreicheren Beispiels, das für die <xref:System.Windows.Media.SolidColorBrush>\-Klasse bereitgestellt wird.  Das vollständige Beispiel finden Sie unter [Beispiel für Pinsel](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## Siehe auch  
 <xref:System.Windows.Media.Brushes>