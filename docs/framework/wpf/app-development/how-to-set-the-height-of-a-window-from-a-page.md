---
title: 'Vorgehensweise: Festlegen der Höhe eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007301"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen der Höhe eines Fensters einer Seite
In diesem Beispiel wird veranschaulicht, wie der Höhe des Fensters aus einem <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> die Höhe des Hostfensters festlegen können, durch Festlegen von <xref:System.Windows.Controls.Page.WindowHeight%2A>. Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters, die darunter gehostet.  
  
> [!NOTE]
>  Die Höhe eines Fensters mit festlegen <xref:System.Windows.Controls.Page.WindowHeight%2A>, <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
