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
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947757"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Vorgehensweise: Im Navigationsverlauf vor oder zurück navigieren
In diesem Beispiel wird veranschaulicht, wie vorwärts oder rückwärts zu Einträge im Navigationsverlauf navigiert.  
  
## <a name="example"></a>Beispiel  
 Code, der von Inhalt in die folgenden Hosts ausgeführt wird, kann vorwärts oder rückwärts durch den Navigationsverlauf einen Eintrag zu einem Zeitpunkt navigieren.  
  
- <xref:System.Windows.Navigation.NavigationWindow> Mithilfe von <xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame> Mithilfe von <xref:System.Windows.Navigation.NavigationService>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Bevor Sie einen Eintrag navigieren können, Sie müssen zuerst überprüfen, dass es Einträge im Navigationsverlauf durch Überprüfen der **CanGoForward** Eigenschaft. Um einen Eintrag zu navigieren, rufen Sie die **GoForward** Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Bevor Sie navigieren können, einen Eintrag zurück, Sie müssen zuerst überprüfen Sie, ob Einträge im Navigationsverlauf zurück durch Überprüfen der **CanGoBack** Eigenschaft. Um Back ein Eintrag zu navigieren, rufen Sie die **GoBack** Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, und **GoBack** werden implementiert, indem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Aufrufen **GoForward**, und es sind keine Einträge im Navigationsverlauf vor, oder rufen Sie **GoBack**, und es sind keine Einträge im Navigationsverlauf zurück, eine <xref:System.InvalidOperationException> ausgelöst.
