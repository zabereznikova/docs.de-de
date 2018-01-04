---
title: 'Gewusst wie: Definieren eines Stifts'
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
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a3bef369f5bdd70588f3934e4199d7d4c703f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-pen"></a>Gewusst wie: Definieren eines Stifts
In diesem Beispiel wird veranschaulicht, wie mit einer <xref:System.Windows.Media.Pen> eine Form werden kann. Erstellen eine einfachen <xref:System.Windows.Media.Pen>, müssen Sie nur einen seiner <xref:System.Windows.Media.Pen.Thickness%2A> und <xref:System.Windows.Media.Pen.Brush%2A>. Sie können eine komplexere Stift erstellen, indem Sie angeben einer <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, und <xref:System.Windows.Media.Pen.EndLineCap%2A>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Windows.Media.Pen> kann eine Form von definiert eine <xref:System.Windows.Media.GeometryDrawing>.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![Konturen eines Stiftes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "Graphicsmm_simple_pen")  
Eine GeometryDrawing
