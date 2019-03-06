---
title: 'Vorgehensweise: Festlegen der Breite eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: fee6d4c9ae9dae03e81cc4be56576763cb59958b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379353"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen der Breite eines Fensters einer Seite
In diesem Beispiel wird veranschaulicht, wie Sie die Breite des Fensters aus Festlegen einer <xref:System.Windows.Controls.Page>.  
  
## <a name="example"></a>Beispiel  
 Ein <xref:System.Windows.Controls.Page> können, legen Sie die Breite des Hostfensters durch Festlegen von <xref:System.Windows.Controls.Page.WindowWidth%2A>. Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters, die darunter gehostet.  
  
> [!NOTE]
>  Die Breite eines Fensters mit festgelegt <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
