---
title: "Gewusst wie: Vorwärts- oder Rückwärtsnavigation mit dem Navigationsverlauf"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78fd9fec6a93c100da6b4e7174376a963ae8beb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Gewusst wie: Vorwärts- oder Rückwärtsnavigation mit dem Navigationsverlauf
In diesem Beispiel wird veranschaulicht, wie mit den Einträgen im Navigationsverlauf vorwärts oder rückwärts navigieren.  
  
## <a name="example"></a>Beispiel  
 Code, der aus Inhalt in die folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf, einen Eintrag zu einem Zeitpunkt navigieren.  
  
-   <xref:System.Windows.Navigation.NavigationWindow>Mithilfe von<xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame>Mithilfe von<xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Bevor Sie einen Eintrag navigieren können, müssen Sie zuerst überprüfen, dass es Einträge im Verlauf der Vorwärtsnavigation durch Überprüfen der **CanGoForward** Eigenschaft. Um einen Eintrag zu navigieren, rufen Sie die **GoForward** Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Bevor Sie navigieren können, einen Eintrag zurück, müssen Sie zunächst überprüfen, dass es Einträge im Navigationsverlauf durch Überprüfen der **CanGoBack** Eigenschaft. Um wieder eine Eintrag zu navigieren, rufen Sie die **GoBack** Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, und **GoBack** werden durch implementiert <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Beim Aufrufen **GoForward**, und im Navigationsverlauf keine Einträge vorhanden sind oder beim Aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf, ein <xref:System.InvalidOperationException> ausgelöst wird.
