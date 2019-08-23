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
# <a name="how-to-navigate-to-a-page"></a>Vorgehensweise: Navigieren zu einer Seite
In diesem Beispiel werden verschiedene Möglichkeiten veranschaulicht, mit denen eine Seite von einem <xref:System.Windows.Navigation.NavigationWindow>aus navigiert werden kann.  
  
## <a name="example"></a>Beispiel  
 Eine <xref:System.Windows.Navigation.NavigationWindow> kann mit einer der folgenden Aktionen zu einer Seite navigieren:  
  
- Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft  
  
- Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> -Methode.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)]kann entweder relativ oder absolut sein. Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
