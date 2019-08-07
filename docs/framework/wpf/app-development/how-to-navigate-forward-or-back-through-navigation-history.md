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
ms.openlocfilehash: 85d3562246170901d83d6314caec5747d52fb9a0
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817962"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="b768d-102">Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren</span><span class="sxs-lookup"><span data-stu-id="b768d-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="b768d-103">In diesem Beispiel wird veranschaulicht, wie vorwärts oder zurück zu Einträgen im Navigationsverlauf navigiert wird.</span><span class="sxs-lookup"><span data-stu-id="b768d-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b768d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b768d-104">Example</span></span>  
 <span data-ttu-id="b768d-105">Code, der aus dem Inhalt der folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf navigieren, jeweils ein Eintrag.</span><span class="sxs-lookup"><span data-stu-id="b768d-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="b768d-106"><xref:System.Windows.Navigation.NavigationWindow>genutzt<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="b768d-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="b768d-107"><xref:System.Windows.Controls.Frame>genutzt<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="b768d-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="b768d-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b768d-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="b768d-109">Bevor Sie einen Eintrag vorwärts navigieren können, müssen Sie zunächst überprüfen, ob im vorwärts Navigationsverlauf Einträge vorhanden sind, indem Sie die **CanGoForward** -Eigenschaft überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b768d-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="b768d-110">Um einen Eintrag vorwärts zu navigieren, rufen Sie die **GoForward** -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b768d-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="b768d-111">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b768d-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="b768d-112">Bevor Sie zu einem Eintrag zurück navigieren können, müssen Sie zunächst überprüfen, ob im Navigationsverlauf zurück Einträge vorhanden sind, indem Sie die Eigenschaft **CanGoBack** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b768d-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="b768d-113">Um zurück zu einem Eintrag zu navigieren, rufen Sie die **GoBack** -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b768d-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="b768d-114">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b768d-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="b768d-115">**"CanGoForward**", " **GoForward**", " **CanGoBack**" und <xref:System.Windows.Navigation.NavigationWindow>" <xref:System.Windows.Controls.Frame> **GoBack** " werden von, und <xref:System.Windows.Navigation.NavigationService>implementiert.</span><span class="sxs-lookup"><span data-stu-id="b768d-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b768d-116">Wenn Sie " **GoForward**" und im Navigationsverlauf "Vorwärts" keine Einträge vorhanden sind oder wenn Sie " **GoBack**" aufgerufen haben und keine Einträge im Navigationsverlauf zurück vorhanden <xref:System.InvalidOperationException> sind, wird eine ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b768d-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
