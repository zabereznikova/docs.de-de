---
title: 'Vorgehensweise: Navigieren Sie zu einer Seite'
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
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa4d0881d7dcdb2c56c66c5617652ec1a2cbc374
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-to-a-page"></a>Vorgehensweise: Navigieren Sie zu einer Seite
Dieses Beispiel veranschaulicht mehrere Möglichkeiten, in dem eine Seite kann navigiert werden, aus, einer <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Beispiel  
 Es ist möglich, dass eine <xref:System.Windows.Navigation.NavigationWindow> zum Navigieren zu einer Seite mit einer der folgenden:  
  
-   Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft  
  
-   Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A>-Methode.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]kann entweder relativ oder absolut sein. Weitere Informationen finden Sie unter [Paket-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Frame>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Navigation.NavigationService>
