---
title: "Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts | Microsoft Docs"
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
  - "Auflisten der Inhalte eines visuellen Objekts [WPF]"
  - "Abrufen des DrawingGroup-Werts eines visuellen Objekts [WPF]"
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts
Das <xref:System.Windows.Media.Drawing>\-Objekt stellt ein Objektmodell für das Auflisten des Inhalts eines <xref:System.Windows.Media.Visual> bereit.  
  
## Beispiel  
 Im folgenden Beispiel wird mit der <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>\-Methode der <xref:System.Windows.Media.DrawingGroup>\-Wert von einem <xref:System.Windows.Media.Visual> abgerufen und aufgelistet.  
  
> [!NOTE]
>  Wenn Sie den Visualinhalt auflisten, rufen Sie <xref:System.Windows.Media.Drawing>\-Objekte ab, und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektorgrafiken.  Weitere Informationen finden Sie unter [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.VisualTreeHelper>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über das WPF\-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)