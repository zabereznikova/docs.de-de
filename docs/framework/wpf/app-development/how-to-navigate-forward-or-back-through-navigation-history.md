---
title: 'Gewusst wie: Vorwärts- oder Rückwärtsnavigation mit dem Navigationsverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: ac3b8b71b6adf04d71cf35edbb042b82c57d8e1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546265"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="df45d-102">Gewusst wie: Vorwärts- oder Rückwärtsnavigation mit dem Navigationsverlauf</span><span class="sxs-lookup"><span data-stu-id="df45d-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="df45d-103">In diesem Beispiel wird veranschaulicht, wie mit den Einträgen im Navigationsverlauf vorwärts oder rückwärts navigieren.</span><span class="sxs-lookup"><span data-stu-id="df45d-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df45d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df45d-104">Example</span></span>  
 <span data-ttu-id="df45d-105">Code, der aus Inhalt in die folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf, einen Eintrag zu einem Zeitpunkt navigieren.</span><span class="sxs-lookup"><span data-stu-id="df45d-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="df45d-106"><xref:System.Windows.Navigation.NavigationWindow> Mithilfe von <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="df45d-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="df45d-107"><xref:System.Windows.Controls.Frame> Mithilfe von <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="df45d-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="df45d-108">Bevor Sie einen Eintrag navigieren können, müssen Sie zuerst überprüfen, dass es Einträge im Verlauf der Vorwärtsnavigation durch Überprüfen der **CanGoForward** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="df45d-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="df45d-109">Um einen Eintrag zu navigieren, rufen Sie die **GoForward** Methode.</span><span class="sxs-lookup"><span data-stu-id="df45d-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="df45d-110">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="df45d-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="df45d-111">Bevor Sie navigieren können, einen Eintrag zurück, müssen Sie zunächst überprüfen, dass es Einträge im Navigationsverlauf durch Überprüfen der **CanGoBack** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="df45d-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="df45d-112">Um wieder eine Eintrag zu navigieren, rufen Sie die **GoBack** Methode.</span><span class="sxs-lookup"><span data-stu-id="df45d-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="df45d-113">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="df45d-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="df45d-114">**CanGoForward**, **GoForward**, **CanGoBack**, und **GoBack** werden durch implementiert <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="df45d-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df45d-115">Beim Aufrufen **GoForward**, und im Navigationsverlauf keine Einträge vorhanden sind oder beim Aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf, ein <xref:System.InvalidOperationException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="df45d-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
