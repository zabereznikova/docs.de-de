---
title: 'Gewusst wie: Aufrufen einer Seitenfunktion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: f170977860a73d339f2d83bc43992e6e2bc4053f
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582051"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="a0dfc-102">Gewusst wie: Aufrufen einer Seitenfunktion</span><span class="sxs-lookup"><span data-stu-id="a0dfc-102">How to: Call a Page Function</span></span>
<span data-ttu-id="a0dfc-103">In diesem Beispiel wird gezeigt, wie eine Seiten Funktion auf einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a0dfc-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0dfc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0dfc-104">Example</span></span>  
 <span data-ttu-id="a0dfc-105">Sie können zu einer Seiten Funktion navigieren, indem Sie einen URI (Uniform Resource Identifier) verwenden, genau wie beim Navigieren zu einer Seite.</span><span class="sxs-lookup"><span data-stu-id="a0dfc-105">You can navigate to a page function using a uniform resource identifier (URI), just as you can when you navigate to a page.</span></span> <span data-ttu-id="a0dfc-106">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0dfc-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="a0dfc-107">Wenn Sie Daten an die Seitenfunktion übergeben möchten, können Sie davon eine Instanz erstellen und die Daten übergeben, indem Sie eine Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="a0dfc-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="a0dfc-108">Wie im folgenden Beispiel gezeigt, können Sie die Daten mithilfe eines nicht Parameter losen Konstruktors übergeben.</span><span class="sxs-lookup"><span data-stu-id="a0dfc-108">Or, as the following example shows, you can pass the data using a non-parameterless constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="a0dfc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0dfc-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
