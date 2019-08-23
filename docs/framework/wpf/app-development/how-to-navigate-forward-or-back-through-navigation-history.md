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
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961349"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren
In diesem Beispiel wird veranschaulicht, wie vorwärts oder zurück zu Einträgen im Navigationsverlauf navigiert wird.  
  
## <a name="example"></a>Beispiel  
 Code, der aus dem Inhalt der folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf navigieren, jeweils ein Eintrag.  
  
- <xref:System.Windows.Navigation.NavigationWindow>genutzt<xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame>genutzt<xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 Bevor Sie einen Eintrag vorwärts navigieren können, müssen Sie zunächst überprüfen, ob im vorwärts Navigationsverlauf Einträge vorhanden sind, indem Sie die **CanGoForward** -Eigenschaft überprüfen. Um einen Eintrag vorwärts zu navigieren, rufen Sie die **GoForward** -Methode auf. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Bevor Sie zu einem Eintrag zurück navigieren können, müssen Sie zunächst überprüfen, ob im Navigationsverlauf zurück Einträge vorhanden sind, indem Sie die Eigenschaft **CanGoBack** überprüfen. Um zurück zu einem Eintrag zu navigieren, rufen Sie die **GoBack** -Methode auf. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **"CanGoForward**", " **GoForward**", " **CanGoBack**" und <xref:System.Windows.Navigation.NavigationWindow>" <xref:System.Windows.Controls.Frame> **GoBack** " werden von, und <xref:System.Windows.Navigation.NavigationService>implementiert.  
  
> [!NOTE]
> Wenn Sie " **GoForward**" und im Navigationsverlauf "Vorwärts" keine Einträge vorhanden sind oder wenn Sie " **GoBack**" aufgerufen haben und keine Einträge im Navigationsverlauf zurück vorhanden <xref:System.InvalidOperationException> sind, wird eine ausgelöst.
