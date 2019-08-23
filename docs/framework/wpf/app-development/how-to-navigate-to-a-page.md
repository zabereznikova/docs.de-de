---
title: 'Vorgehensweise: Navigieren zu einer Seite'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 38814268c9bb271ad3d88d549fb6ec4c6cbfed40
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966025"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="32bf5-102">Vorgehensweise: Navigieren zu einer Seite</span><span class="sxs-lookup"><span data-stu-id="32bf5-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="32bf5-103">In diesem Beispiel werden verschiedene Möglichkeiten veranschaulicht, mit denen eine Seite von einem <xref:System.Windows.Navigation.NavigationWindow>aus navigiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="32bf5-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32bf5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32bf5-104">Example</span></span>  
 <span data-ttu-id="32bf5-105">Eine <xref:System.Windows.Navigation.NavigationWindow> kann mit einer der folgenden Aktionen zu einer Seite navigieren:</span><span class="sxs-lookup"><span data-stu-id="32bf5-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="32bf5-106">Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32bf5-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="32bf5-107">Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="32bf5-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]<span data-ttu-id="32bf5-108">kann entweder relativ oder absolut sein.</span><span class="sxs-lookup"><span data-stu-id="32bf5-108">can be either relative or absolute.</span></span> <span data-ttu-id="32bf5-109">Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="32bf5-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bf5-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32bf5-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
