---
title: 'Gewusst wie: Definieren eines Stifts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 7c5be5eff06df55e465f3e34646ba1c34e8b7e07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559854"
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="f4cf1-102">Gewusst wie: Definieren eines Stifts</span><span class="sxs-lookup"><span data-stu-id="f4cf1-102">How to: Define a Pen</span></span>
<span data-ttu-id="f4cf1-103">In diesem Beispiel wird veranschaulicht, wie mit einer <xref:System.Windows.Media.Pen> eine Form werden kann.</span><span class="sxs-lookup"><span data-stu-id="f4cf1-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="f4cf1-104">Erstellen eine einfachen <xref:System.Windows.Media.Pen>, müssen Sie nur einen seiner <xref:System.Windows.Media.Pen.Thickness%2A> und <xref:System.Windows.Media.Pen.Brush%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4cf1-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="f4cf1-105">Sie können eine komplexere Stift erstellen, indem Sie angeben einer <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, und <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4cf1-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4cf1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4cf1-106">Example</span></span>  
 <span data-ttu-id="f4cf1-107">Im folgenden Beispiel wird eine <xref:System.Windows.Media.Pen> kann eine Form von definiert eine <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="f4cf1-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="f4cf1-108">![Konturen eines Stiftes](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "Graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="f4cf1-108">![Outlines produces by a Pen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="f4cf1-109">Eine GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="f4cf1-109">A GeometryDrawing</span></span>
