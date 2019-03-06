---
title: 'Vorgehensweise: Rückwärtsnavigation im Navigationsverlauf'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: c489a1593b3d1f22fe1ad6e648d3f8a3f7a6cd44
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377767"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Vorgehensweise: Rückwärtsnavigation im Navigationsverlauf
In diesem Beispiel wird veranschaulicht, wie auf Einträge im Navigationsverlauf navigiert.  
  
## <a name="example"></a>Beispiel  
 Code, der Inhalt ausgeführt wird, die in gehostet ist eine <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> mit <xref:System.Windows.Navigation.NavigationService>, oder [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] können Rückwärtsnavigation im Navigationsverlauf, einen Eintrag zu einem Zeitpunkt.  
  
 Navigation eine Eingabe erforderlich ist, zuerst die Prüfung, es Einträge im Navigationsverlauf zurück, indem sind die **CanGoBack** Eigenschaft vor der Navigation einen Eintrag zurück, durch den Aufruf der **GoBack** -Methode. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** und **GoBack** werden implementiert, indem <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, und <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Wenn Sie aufrufen **GoBack**, und es sind keine Einträge im Navigationsverlauf zurück, eine <xref:System.InvalidOperationException> ausgelöst wird.
