---
title: "Gewusst wie: Anpassen der Gr&#246;&#223;e des Ziehpunkts auf einer Bildlaufleiste | Microsoft Docs"
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
  - "Anpassen der Größe des Ziehpunkts"
  - "ScrollBar-Steuerelement"
  - "Ziehpunktgröße"
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Anpassen der Gr&#246;&#223;e des Ziehpunkts auf einer Bildlaufleiste
In diesem Thema wird erläutert, wie der <xref:System.Windows.Controls.Primitives.Thumb> einer <xref:System.Windows.Controls.Primitives.ScrollBar> auf eine feste Größe festgelegt und eine minimale Größe für den <xref:System.Windows.Controls.Primitives.Thumb> einer <xref:System.Windows.Controls.Primitives.ScrollBar> angegeben wird.  
  
## Beispiel  
  
## Beschreibung  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.ScrollBar> erstellt, die einen <xref:System.Windows.Controls.Primitives.Thumb> mit einer festen Größe besitzt.  Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A>\-Eigenschaft für den <xref:System.Windows.Controls.Primitives.Thumb> auf <xref:System.Double.NaN> festgelegt, außerdem die Höhe für den <xref:System.Windows.Controls.Primitives.Thumb>.  Um eine horizontale <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> fester Breite zu erstellen, legen Sie die Breite für den <xref:System.Windows.Controls.Primitives.Thumb> fest.  
  
## Code  
 [!code-xml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## Beschreibung  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.ScrollBar> erstellt, die einen <xref:System.Windows.Controls.Primitives.Thumb> mit einer minimalen Größe besitzt.  Im Beispiel wird der <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>\-Wert festgelegt.  Um eine horizontale <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> zu erstellen, der eine minimale Breite hat, legen Sie den <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> fest.  
  
## Code  
 [!code-xml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## Siehe auch  
 [ScrollBar\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)