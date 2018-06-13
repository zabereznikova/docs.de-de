---
title: 'Vorgehensweise: Aktualisieren einer Seite'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
ms.openlocfilehash: 27735450360206e0a15ecae00cc9d45f93e4e838
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546529"
---
# <a name="how-to-refresh-a-page"></a><span data-ttu-id="be9eb-102">Vorgehensweise: Aktualisieren einer Seite</span><span class="sxs-lookup"><span data-stu-id="be9eb-102">How to: Refresh a Page</span></span>
<span data-ttu-id="be9eb-103">In diesem Beispiel wird gezeigt, wie zum Aufrufen der <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> Methode zum Aktualisieren des aktuellen Inhalts in einen <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="be9eb-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> method to refresh the current content in a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be9eb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be9eb-104">Example</span></span>  
 <span data-ttu-id="be9eb-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> aktualisiert den aktuellen Inhalt in einem <xref:System.Windows.Navigation.NavigationWindow> aus ihrer Quelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="be9eb-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> refreshes the current content in a <xref:System.Windows.Navigation.NavigationWindow> to be reloaded from its source.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
