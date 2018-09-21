---
title: 'Vorgehensweise: Navigieren durch den Navigationsverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 7266c9486524e962a859c34c9be5ab8f6d7bf7d5
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46492106"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="52698-102">Vorgehensweise: Navigieren durch den Navigationsverlauf</span><span class="sxs-lookup"><span data-stu-id="52698-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="52698-103">In diesem Beispiel wird veranschaulicht, wie auf Einträge im Navigationsverlauf navigiert.</span><span class="sxs-lookup"><span data-stu-id="52698-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52698-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52698-104">Example</span></span>  
 <span data-ttu-id="52698-105">Code, der Inhalt ausgeführt wird, die in gehostet ist eine <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> mit <xref:System.Windows.Navigation.NavigationService>, oder [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] können Rückwärtsnavigation im Navigationsverlauf, einen Eintrag zu einem Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="52698-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="52698-106">Navigation eine Eingabe erforderlich ist, zuerst die Prüfung, es Einträge im Navigationsverlauf zurück, indem sind die **CanGoBack** Eigenschaft vor der Navigation einen Eintrag zurück, durch den Aufruf der **GoBack** -Methode.</span><span class="sxs-lookup"><span data-stu-id="52698-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="52698-107">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="52698-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="52698-108">**CanGoBack** und **GoBack** werden implementiert, indem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="52698-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52698-109">Wenn Sie aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf zurück, eine <xref:System.InvalidOperationException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="52698-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
