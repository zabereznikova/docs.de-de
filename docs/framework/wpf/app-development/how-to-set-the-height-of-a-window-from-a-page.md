---
title: "Vorgehensweise: Festlegen der Höhe eines Fensters von einer Seite"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 002e75542c1dbbe1cfaa122898801dd5babf054f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="454b7-102">Vorgehensweise: Festlegen der Höhe eines Fensters von einer Seite</span><span class="sxs-lookup"><span data-stu-id="454b7-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="454b7-103">In diesem Beispiel wird veranschaulicht, wie der Höhe des Fensters aus einem <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="454b7-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="454b7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="454b7-104">Example</span></span>  
 <span data-ttu-id="454b7-105">Ein <xref:System.Windows.Controls.Page> kann durch Festlegen der Höhe der entsprechende Hostfenster festgelegt <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="454b7-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="454b7-106">Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters aufweisen, die diese hostet.</span><span class="sxs-lookup"><span data-stu-id="454b7-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="454b7-107">Die Höhe eines Fensters mithilfe festzulegende <xref:System.Windows.Controls.Page.WindowHeight%2A>ein <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.</span><span class="sxs-lookup"><span data-stu-id="454b7-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
