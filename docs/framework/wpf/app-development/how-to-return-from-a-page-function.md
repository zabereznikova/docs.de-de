---
title: "Gewusst wie: Zurückgeben aus einer Seitenfunktion"
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
- returning from page functions [WPF]
- page functions [WPF], returning from
- functions [WPF], returning from
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f96f97645a6e67ac000219b32290f75e8ab0585
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-return-from-a-page-function"></a><span data-ttu-id="a0d28-102">Gewusst wie: Zurückgeben aus einer Seitenfunktion</span><span class="sxs-lookup"><span data-stu-id="a0d28-102">How to: Return from a Page Function</span></span>
<span data-ttu-id="a0d28-103">In diesem Beispiel wird gezeigt, wie ein Ergebnis von einer Seitenfunktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0d28-103">This example shows how to return a result from a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0d28-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0d28-104">Example</span></span>  
 <span data-ttu-id="a0d28-105">Um von einer Seitenfunktion zurückgegeben wird, müssen Sie rufen <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> und übergeben Sie eine Instanz des <xref:System.Windows.Navigation.ReturnEventArgs%601>.</span><span class="sxs-lookup"><span data-stu-id="a0d28-105">To return from a page function, you need to call <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> and pass an instance of <xref:System.Windows.Navigation.ReturnEventArgs%601>.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="a0d28-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0d28-106">See Also</span></span>  
 <xref:System.Windows.Navigation.PageFunction%601>
