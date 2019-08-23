---
title: 'Vorgehensweise: Festlegen der Breite eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940774"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen der Breite eines Fensters einer Seite
In diesem Beispiel wird veranschaulicht, wie die Breite des Fensters von einem <xref:System.Windows.Controls.Page>festgelegt wird.  
  
## <a name="example"></a>Beispiel  
 Eine <xref:System.Windows.Controls.Page> kann die Breite des Host Fensters <xref:System.Windows.Controls.Page.WindowWidth%2A>durch Festlegen von festlegen. Diese Eigenschaft ermöglicht es <xref:System.Windows.Controls.Page> dem nicht, explizite Informationen über den Typ des Fensters zu haben, in dem es gehostet wird.  
  
> [!NOTE]
> Um die Breite eines Fensters mit <xref:System.Windows.Controls.Page.WindowWidth%2A>festzulegen, muss ein <xref:System.Windows.Controls.Page> untergeordnetes Element eines Fensters sein.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
