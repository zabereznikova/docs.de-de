---
title: 'Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543169"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="f724e-102">Gewusst wie: Datenbindung an ein InkCanvas-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f724e-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="f724e-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f724e-103">Example</span></span>  
 <span data-ttu-id="f724e-104">Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaft ein <xref:System.Windows.Controls.InkCanvas> in eine andere <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="f724e-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="f724e-105">Das folgende Beispiel veranschaulicht das Binden der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft mit einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f724e-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="f724e-106">Das folgende Beispiel deklariert zwei <xref:System.Windows.Controls.InkCanvas> -Objekte in XAML und stellt die Datenbindung zwischen ihnen und anderen Datenquellen her.</span><span class="sxs-lookup"><span data-stu-id="f724e-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="f724e-107">Die erste <xref:System.Windows.Controls.InkCanvas>namens `ic`, mit zwei Datenquellen gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="f724e-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="f724e-108">Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> und <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften auf `ic` gebunden <xref:System.Windows.Controls.ListBox> Objekte, die wiederum in der XAML-definierte Arrays gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="f724e-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="f724e-109">Die <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, und <xref:System.Windows.Controls.InkCanvas.Strokes%2A> Eigenschaften des zweiten <xref:System.Windows.Controls.InkCanvas> gebunden sind mit dem ersten <xref:System.Windows.Controls.InkCanvas>, `ic`.</span><span class="sxs-lookup"><span data-stu-id="f724e-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
