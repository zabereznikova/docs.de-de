---
title: 'Vorgehensweise: Festlegen der Breite eines Fensters von einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: a0ae0e136e0b7f1cd2a2ec56455e14723e8fa306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545989"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="fee97-102">Vorgehensweise: Festlegen der Breite eines Fensters von einer Seite</span><span class="sxs-lookup"><span data-stu-id="fee97-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="fee97-103">In diesem Beispiel wird veranschaulicht, wie die Breite des Fensters aus Festlegen einer <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="fee97-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fee97-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fee97-104">Example</span></span>  
 <span data-ttu-id="fee97-105">Ein <xref:System.Windows.Controls.Page> kann durch Festlegen der Breite der entsprechende Hostfenster festgelegt <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span><span class="sxs-lookup"><span data-stu-id="fee97-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="fee97-106">Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters aufweisen, die diese hostet.</span><span class="sxs-lookup"><span data-stu-id="fee97-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fee97-107">Die Breite des Fensters festzulegende <xref:System.Windows.Controls.Page.WindowWidth%2A>ein <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.</span><span class="sxs-lookup"><span data-stu-id="fee97-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
