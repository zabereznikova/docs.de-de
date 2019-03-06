---
title: 'Vorgehensweise: Aufrufen von Seitenfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 288edec51a690be844aaa913c368496648a7811b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375167"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="67bf7-102">Vorgehensweise: Aufrufen von Seitenfunktionen</span><span class="sxs-lookup"><span data-stu-id="67bf7-102">How to: Call a Page Function</span></span>
<span data-ttu-id="67bf7-103">Dieses Beispiel zeigt, wie Sie eine Seitenfunktion auf Aufrufen einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite.</span><span class="sxs-lookup"><span data-stu-id="67bf7-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67bf7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67bf7-104">Example</span></span>  
 <span data-ttu-id="67bf7-105">Gelangen Sie zu einer Seite mit einem [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]genau wie können Sie beim Navigieren zu einer Seite.</span><span class="sxs-lookup"><span data-stu-id="67bf7-105">You can navigate to a page function using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], just as you can when you navigate to a page.</span></span> <span data-ttu-id="67bf7-106">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="67bf7-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="67bf7-107">Wenn Sie Daten an die Seitenfunktion übergeben möchten, können Sie davon eine Instanz erstellen und die Daten übergeben, indem Sie eine Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="67bf7-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="67bf7-108">Sie können die Daten auch übergeben, indem Sie einen nicht standardmäßigen Konstruktor verwenden.</span><span class="sxs-lookup"><span data-stu-id="67bf7-108">Or, as the following example shows, you can pass the data using a non-default constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="67bf7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67bf7-109">See also</span></span>
- <xref:System.Windows.Navigation.PageFunction%601>
