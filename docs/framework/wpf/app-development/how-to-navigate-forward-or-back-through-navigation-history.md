---
title: 'Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 00a41fcf85583ec0d081a2fa099f3a77cfcd2900
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625359"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="a1610-102">Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren</span><span class="sxs-lookup"><span data-stu-id="a1610-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="a1610-103">In diesem Beispiel wird veranschaulicht, wie vorwärts oder rückwärts zu Einträge im Navigationsverlauf navigiert.</span><span class="sxs-lookup"><span data-stu-id="a1610-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1610-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1610-104">Example</span></span>  
 <span data-ttu-id="a1610-105">Code, der von Inhalt in die folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf einen Eintrag zu einem Zeitpunkt navigieren.</span><span class="sxs-lookup"><span data-stu-id="a1610-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="a1610-106"><xref:System.Windows.Navigation.NavigationWindow> Mithilfe von <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="a1610-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="a1610-107"><xref:System.Windows.Controls.Frame> Mithilfe von <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="a1610-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="a1610-108">Bevor Sie einen Eintrag navigieren können, Sie müssen zuerst überprüfen, dass es Einträge im Navigationsverlauf durch Überprüfen der **CanGoForward** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1610-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="a1610-109">Um einen Eintrag zu navigieren, rufen Sie die **GoForward** Methode.</span><span class="sxs-lookup"><span data-stu-id="a1610-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="a1610-110">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a1610-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="a1610-111">Bevor Sie navigieren können, einen Eintrag zurück, Sie müssen zuerst überprüfen Sie, ob Einträge im Navigationsverlauf zurück durch Überprüfen der **CanGoBack** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1610-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="a1610-112">Um Back ein Eintrag zu navigieren, rufen Sie die **GoBack** Methode.</span><span class="sxs-lookup"><span data-stu-id="a1610-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="a1610-113">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a1610-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="a1610-114">**CanGoForward**, **GoForward**, **CanGoBack**, und **GoBack** werden implementiert, indem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="a1610-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1610-115">Aufrufen **GoForward**, und es sind keine Einträge im Navigationsverlauf vor, oder rufen Sie **GoBack**, und es sind keine Einträge im Navigationsverlauf zurück, eine <xref:System.InvalidOperationException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="a1610-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
