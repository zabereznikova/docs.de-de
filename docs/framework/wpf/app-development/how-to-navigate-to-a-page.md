---
title: 'Vorgehensweise: Navigieren Sie zu einer Seite'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: a5a0e7a8e7effac7c51f4dee92d30de56d60d90c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369339"
---
# <a name="how-to-navigate-to-a-page"></a>Vorgehensweise: Navigieren Sie zu einer Seite
Dieses Beispiel veranschaulicht mehrere Möglichkeiten, die in der eine Seite werden, von navigiert kann einem <xref:System.Windows.Navigation.NavigationWindow>.  
  
## <a name="example"></a>Beispiel  
 Es ist möglich, dass eine <xref:System.Windows.Navigation.NavigationWindow> Navigieren zu einer Seite mit einer der folgenden:  
  
-   Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft  
  
-   Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> -Methode.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_uri#initcap#plural](../../../../includes/tlasharptla-urisharpinitcapsharpplural-md.md)] Dies kann entweder relativ oder absolut sein. Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
