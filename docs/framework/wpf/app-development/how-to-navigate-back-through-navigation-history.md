---
title: 'Vorgehensweise: Im Navigationsverlauf zurück navigieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817977"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Vorgehensweise: Im Navigationsverlauf zurück navigieren
In diesem Beispiel wird veranschaulicht, wie Sie zu Einträgen im Navigationsverlauf zurück navigieren.  
  
## <a name="example"></a>Beispiel  
 Code, der von Inhalten ausgeführt wird, die in einem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> mithilfe <xref:System.Windows.Navigation.NavigationService>von oder Internet Explorer gehostet werden, kann durch den Navigationsverlauf, einen Eintrag gleichzeitig, navigieren.  
  
 Wenn Sie zu einem Eintrag zurück navigieren, müssen Sie zunächst überprüfen, ob Einträge im Navigationsverlauf zurück vorhanden sind, indem Sie die **CanGoBack** -Eigenschaft überprüfen, bevor Sie einen Eintrag durch Aufrufen der **GoBack** -Methode zurück navigieren. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** und **GoBack** werden von <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>und <xref:System.Windows.Navigation.NavigationService>implementiert.  
  
> [!NOTE]
>  Wenn Sie " **GoBack**" aufzurufen und keine Einträge im Navigationsverlauf zurück vorhanden sind <xref:System.InvalidOperationException> , wird eine ausgelöst.
