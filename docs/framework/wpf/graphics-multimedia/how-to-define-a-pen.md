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
ms.openlocfilehash: c173b895f67164152d5930efc6a385bc480aaa81
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="86fe7-102">Gewusst wie: Definieren eines Stifts</span><span class="sxs-lookup"><span data-stu-id="86fe7-102">How to: Define a Pen</span></span>
<span data-ttu-id="86fe7-103">In diesem Beispiel wird veranschaulicht, wie mit einer <xref:System.Windows.Media.Pen> eine Form werden kann.</span><span class="sxs-lookup"><span data-stu-id="86fe7-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="86fe7-104">Erstellen eine einfachen <xref:System.Windows.Media.Pen>, müssen Sie nur einen seiner <xref:System.Windows.Media.Pen.Thickness%2A> und <xref:System.Windows.Media.Pen.Brush%2A>.</span><span class="sxs-lookup"><span data-stu-id="86fe7-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="86fe7-105">Sie können eine komplexere Stift erstellen, indem Sie angeben einer <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, und <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="86fe7-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86fe7-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86fe7-106">Example</span></span>  
 <span data-ttu-id="86fe7-107">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Pen> kann eine Form von definiert eine <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="86fe7-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="86fe7-108">![Konturen eines Stiftes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "Graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="86fe7-108">![Outlines produces by a Pen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="86fe7-109">Eine GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="86fe7-109">A GeometryDrawing</span></span>
