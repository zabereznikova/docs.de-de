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
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961349"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="e5e29-102">Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren</span><span class="sxs-lookup"><span data-stu-id="e5e29-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="e5e29-103">In diesem Beispiel wird veranschaulicht, wie vorwärts oder zurück zu Einträgen im Navigationsverlauf navigiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5e29-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5e29-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5e29-104">Example</span></span>  
 <span data-ttu-id="e5e29-105">Code, der aus dem Inhalt der folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf navigieren, jeweils ein Eintrag.</span><span class="sxs-lookup"><span data-stu-id="e5e29-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="e5e29-106"><xref:System.Windows.Navigation.NavigationWindow>genutzt<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e5e29-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="e5e29-107"><xref:System.Windows.Controls.Frame>genutzt<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="e5e29-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="e5e29-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e5e29-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="e5e29-109">Bevor Sie einen Eintrag vorwärts navigieren können, müssen Sie zunächst überprüfen, ob im vorwärts Navigationsverlauf Einträge vorhanden sind, indem Sie die **CanGoForward** -Eigenschaft überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e5e29-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="e5e29-110">Um einen Eintrag vorwärts zu navigieren, rufen Sie die **GoForward** -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="e5e29-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="e5e29-111">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e5e29-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="e5e29-112">Bevor Sie zu einem Eintrag zurück navigieren können, müssen Sie zunächst überprüfen, ob im Navigationsverlauf zurück Einträge vorhanden sind, indem Sie die Eigenschaft **CanGoBack** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e5e29-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="e5e29-113">Um zurück zu einem Eintrag zu navigieren, rufen Sie die **GoBack** -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="e5e29-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="e5e29-114">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e5e29-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="e5e29-115">**"CanGoForward**", " **GoForward**", " **CanGoBack**" und <xref:System.Windows.Navigation.NavigationWindow>" <xref:System.Windows.Controls.Frame> **GoBack** " werden von, und <xref:System.Windows.Navigation.NavigationService>implementiert.</span><span class="sxs-lookup"><span data-stu-id="e5e29-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5e29-116">Wenn Sie " **GoForward**" und im Navigationsverlauf "Vorwärts" keine Einträge vorhanden sind oder wenn Sie " **GoBack**" aufgerufen haben und keine Einträge im Navigationsverlauf zurück vorhanden <xref:System.InvalidOperationException> sind, wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e5e29-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
