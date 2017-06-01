---
title: "Gewusst wie: Definieren eines Stifts | Microsoft Docs"
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
  - "Erstellen, Stifte"
  - "Stifte, Definieren"
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 2
---
# Gewusst wie: Definieren eines Stifts
Dieses Beispiel zeigt, wie Sie einen <xref:System.Windows.Media.Pen> verwenden, um eine Form zu gliedern.  Um einen einfachen <xref:System.Windows.Media.Pen> zu erstellen, müssen Sie nur Werte für <xref:System.Windows.Media.Pen.Thickness%2A> und <xref:System.Windows.Media.Pen.Brush%2A> angeben.  Sie können auch umfangreichere Stifte erstellen, indem Sie Werte für <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A> und <xref:System.Windows.Media.Pen.EndLineCap%2A> angeben.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Media.Pen> verwendet, um eine Form zu gliedern, die mithilfe von <xref:System.Windows.Media.GeometryDrawing> definiert ist.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![Mit einem Stift erstellte Konturen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.png "graphicsmm\_simple\_pen")  
  
        Eine GeometryDrawing