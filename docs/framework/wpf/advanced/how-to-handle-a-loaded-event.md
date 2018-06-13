---
title: 'Gewusst wie: Behandeln eines geladenen Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 6f3520fc3bc2a64d76083af415588ff819890eb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544191"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="13c7b-102">Gewusst wie: Behandeln eines geladenen Ereignisses</span><span class="sxs-lookup"><span data-stu-id="13c7b-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="13c7b-103">In diesem Beispiel wird gezeigt, wie behandelt die <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> Ereignisses, und ein entsprechendes Szenario für die Behandlung dieses Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="13c7b-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="13c7b-104">Der Ereignishandler erstellt ein <xref:System.Windows.Controls.Button> beim Laden der Seite.</span><span class="sxs-lookup"><span data-stu-id="13c7b-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c7b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13c7b-105">Example</span></span>  
 <span data-ttu-id="13c7b-106">Im folgenden Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zusammen mit einem Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="13c7b-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="13c7b-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13c7b-107">See Also</span></span>  
 <xref:System.Windows.FrameworkElement>  
 [<span data-ttu-id="13c7b-108">Objektlebensdauer-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="13c7b-108">Object Lifetime Events</span></span>](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)  
 [<span data-ttu-id="13c7b-109">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="13c7b-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="13c7b-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="13c7b-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
