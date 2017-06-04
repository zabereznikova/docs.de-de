---
title: "Gewusst wie: Anwenden eines F&#252;hrungsliniensatzes auf eine Zeichnung | Microsoft Docs"
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
  - "Grafiken [WPF], GuidelineSet-Eigenschaft"
  - "GuidelineSet-Eigenschaft, Anwenden auf Zeichnungen"
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Anwenden eines F&#252;hrungsliniensatzes auf eine Zeichnung
In diesem Beispiel wird das Anwenden eines <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup> erläutert.  
  
 Die <xref:System.Windows.Media.DrawingGroup>\-Klasse ist der einzige Typ von <xref:System.Windows.Media.Drawing>, der über eine <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>\-Eigenschaft verfügt.  Wenn Sie einen <xref:System.Windows.Media.GuidelineSet> auf einen anderen Typ von <xref:System.Windows.Media.Drawing> anwenden möchten, fügen Sie ihn einer <xref:System.Windows.Media.DrawingGroup> hinzu und wenden den <xref:System.Windows.Media.GuidelineSet> auf die <xref:System.Windows.Media.DrawingGroup> an.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei nahezu identische <xref:System.Windows.Media.DrawingGroup>\-Objekte erstellt. Der einzige Unterschied besteht darin, dass im Gegensatz zum ersten Objekt das zweite Objekt <xref:System.Windows.Media.DrawingGroup> über einen <xref:System.Windows.Media.GuidelineSet> verfügt.  
  
 Die folgende Abbildung zeigt die Ausgabe des Codebeispiels.  Da die Unterschiede im Renderverhalten beider <xref:System.Windows.Media.DrawingGroup>\-Objekte so gering sind, werden Teile der Zeichnung vergrößert dargestellt.  
  
 ![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm\_drawinggroup\_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.GuidelineSet>   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)