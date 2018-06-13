---
title: 'Vorgehensweise: Festlegen des Titels einer Seite eines Fensters'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: e69812b59783717b7b9c832d4e8ab01ab42827c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546184"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen des Titels einer Seite eines Fensters
In diesem Beispiel wird gezeigt, wie in der den Titel des Fensters Festlegen einer <xref:System.Windows.Controls.Page> gehostet wird.  
  
## <a name="example"></a>Beispiel  
 Eine Seite kann ändern Sie den Titel des Fensters, das sie durch Festlegen hostet der <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft, wie folgt:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Festlegen der <xref:System.Windows.Controls.Page.Title%2A> Eigenschaft einer Seite ändert sich nicht auf den Wert des Window-Titel. Stattdessen <xref:System.Windows.Controls.Page.Title%2A> gibt den Namen eines Eintrags Seite im Navigationsverlauf an.
