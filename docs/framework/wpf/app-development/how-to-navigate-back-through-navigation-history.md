---
title: 'Vorgehensweise: Navigieren durch den Navigationsverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 7266c9486524e962a859c34c9be5ab8f6d7bf7d5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206022"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Vorgehensweise: Navigieren durch den Navigationsverlauf
In diesem Beispiel wird veranschaulicht, wie auf Einträge im Navigationsverlauf navigiert.  
  
## <a name="example"></a>Beispiel  
 Code, der Inhalt ausgeführt wird, die in gehostet ist eine <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> mit <xref:System.Windows.Navigation.NavigationService>, oder [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] können Rückwärtsnavigation im Navigationsverlauf, einen Eintrag zu einem Zeitpunkt.  
  
 Navigation eine Eingabe erforderlich ist, zuerst die Prüfung, es Einträge im Navigationsverlauf zurück, indem sind die **CanGoBack** Eigenschaft vor der Navigation einen Eintrag zurück, durch den Aufruf der **GoBack** -Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** und **GoBack** werden implementiert, indem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Wenn Sie aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf zurück, eine <xref:System.InvalidOperationException> ausgelöst wird.
