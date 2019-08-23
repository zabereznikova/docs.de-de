---
title: 'Vorgehensweise: Festlegen der Höhe eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940798"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="92c82-102">Vorgehensweise: Festlegen der Höhe eines Fensters einer Seite</span><span class="sxs-lookup"><span data-stu-id="92c82-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="92c82-103">In diesem Beispiel wird veranschaulicht, wie die Höhe des Fensters von einem <xref:System.Windows.Controls.Page>festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="92c82-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92c82-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92c82-104">Example</span></span>  
 <span data-ttu-id="92c82-105">Ein <xref:System.Windows.Controls.Page> kann die Höhe des Host Fensters durch Festlegen <xref:System.Windows.Controls.Page.WindowHeight%2A>von festlegen.</span><span class="sxs-lookup"><span data-stu-id="92c82-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="92c82-106">Diese Eigenschaft ermöglicht es <xref:System.Windows.Controls.Page> dem nicht, explizite Informationen über den Typ des Fensters zu haben, in dem es gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="92c82-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92c82-107">Um die Höhe eines Fensters mit <xref:System.Windows.Controls.Page.WindowHeight%2A>festzulegen, muss ein <xref:System.Windows.Controls.Page> untergeordnetes Element eines Fensters sein.</span><span class="sxs-lookup"><span data-stu-id="92c82-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
