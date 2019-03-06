---
title: 'Vorgehensweise: Navigieren Sie zu einer Seite'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: a5a0e7a8e7effac7c51f4dee92d30de56d60d90c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369339"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="8c05f-102">Vorgehensweise: Navigieren Sie zu einer Seite</span><span class="sxs-lookup"><span data-stu-id="8c05f-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="8c05f-103">Dieses Beispiel veranschaulicht mehrere Möglichkeiten, die in der eine Seite werden, von navigiert kann einem <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="8c05f-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c05f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c05f-104">Example</span></span>  
 <span data-ttu-id="8c05f-105">Es ist möglich, dass eine <xref:System.Windows.Navigation.NavigationWindow> Navigieren zu einer Seite mit einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="8c05f-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
-   <span data-ttu-id="8c05f-106">Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c05f-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
-   <span data-ttu-id="8c05f-107">Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="8c05f-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] <span data-ttu-id="8c05f-108">Dies kann entweder relativ oder absolut sein.</span><span class="sxs-lookup"><span data-stu-id="8c05f-108">can be either relative or absolute.</span></span> <span data-ttu-id="8c05f-109">Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="8c05f-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c05f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c05f-110">See also</span></span>
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
