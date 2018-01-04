---
title: 'Vorgehensweise: Navigieren durch den Navigationsverlauf'
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
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3bfc809dbe76c17859cb3fcd83f8a293a24b308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Vorgehensweise: Navigieren durch den Navigationsverlauf
In diesem Beispiel wird veranschaulicht, wie mit den Einträgen im Navigationsverlauf navigieren.  
  
## <a name="example"></a>Beispiel  
 Code, der aus Inhalt ausgeführt wird, die in gehostet ist ein <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> verwenden <xref:System.Windows.Navigation.NavigationService>, oder [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] navigieren können, durch den Navigationsverlauf, einen Eintrag zu einem Zeitpunkt.  
  
 Navigieren durch eine Eingabe erforderlich ist, überprüft zuerst, Einträge im Navigationsverlauf, durch Überprüfung vorhanden sind die **CanGoBack** -Eigenschaft, bevor ein Eintrag zurück navigiert wird durch Aufrufen der **GoBack** Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** und **GoBack** werden durch implementiert <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Beim Aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf, ein <xref:System.InvalidOperationException> ausgelöst wird.
