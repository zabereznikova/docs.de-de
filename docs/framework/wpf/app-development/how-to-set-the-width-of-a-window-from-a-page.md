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
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="34029-102">Vorgehensweise: Festlegen der Breite eines Fensters einer Seite</span><span class="sxs-lookup"><span data-stu-id="34029-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="34029-103">In diesem Beispiel wird veranschaulicht, wie Sie die Breite des Fensters aus Festlegen einer <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="34029-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34029-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34029-104">Example</span></span>  
 <span data-ttu-id="34029-105">Ein <xref:System.Windows.Controls.Page> können, legen Sie die Breite des Hostfensters durch Festlegen von <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span><span class="sxs-lookup"><span data-stu-id="34029-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="34029-106">Diese Eigenschaft ermöglicht die <xref:System.Windows.Controls.Page> keine explizite Kenntnisse in den Typ des Fensters, die darunter gehostet.</span><span class="sxs-lookup"><span data-stu-id="34029-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34029-107">Die Breite eines Fensters mit festgelegt <xref:System.Windows.Controls.Page.WindowWidth%2A>, <xref:System.Windows.Controls.Page> muss das untergeordnete Element eines Fensters.</span><span class="sxs-lookup"><span data-stu-id="34029-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
