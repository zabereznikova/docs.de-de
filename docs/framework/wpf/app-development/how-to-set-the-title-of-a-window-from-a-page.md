---
title: 'Vorgehensweise: Festlegen des Titels eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940783"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="dfb0b-102">Vorgehensweise: Festlegen des Titels eines Fensters einer Seite</span><span class="sxs-lookup"><span data-stu-id="dfb0b-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="dfb0b-103">Dieses Beispiel zeigt, wie Sie den Titel des Fensters festlegen, in dem <xref:System.Windows.Controls.Page> ein gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb0b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfb0b-104">Example</span></span>  
 <span data-ttu-id="dfb0b-105">Eine Seite kann den Titel des Fensters, in dem Sie gehostet wird, ändern, <xref:System.Windows.Controls.Page.WindowTitle%2A> indem die-Eigenschaft wie folgt festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="dfb0b-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <span data-ttu-id="dfb0b-106">Wenn Sie <xref:System.Windows.Controls.Page.Title%2A> die-Eigenschaft einer Seite festlegen, wird der Wert des Fenster Titels nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="dfb0b-107"><xref:System.Windows.Controls.Page.Title%2A> Stattdessen gibt den Namen eines Seiten Eintrags im Navigationsverlauf an.</span><span class="sxs-lookup"><span data-stu-id="dfb0b-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
