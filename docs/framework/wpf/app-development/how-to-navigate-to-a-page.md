---
title: 'Gewusst wie: Navigieren zu einer Seite'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582536"
---
# <a name="how-to-navigate-to-a-page"></a>Gewusst wie: Navigieren zu einer Seite
In diesem Beispiel werden verschiedene Möglichkeiten veranschaulicht, mit denen eine Seite von einem <xref:System.Windows.Navigation.NavigationWindow> aus navigiert werden kann.  
  
## <a name="example"></a>Beispiel  
 Es ist möglich, dass ein <xref:System.Windows.Navigation.NavigationWindow> zu einer Seite navigiert, indem eine der folgenden Aktionen verwendet wird:  
  
- Die <xref:System.Windows.Navigation.NavigationWindow.Source%2A>-Eigenschaft  
  
- Die <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> -Methode.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> Uniform Resource Identifier (URIs) kann entweder relativ oder absolut sein. Weitere Informationen finden Sie unter [Paket-URI in WPF](pack-uris-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
