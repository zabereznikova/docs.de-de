---
title: 'Vorgehensweise: Behandeln eines geladenen Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: b8cd2f5e9d848cebb712e7b4930ca39efe48ecc0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122550"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="0c974-102">Vorgehensweise: Behandeln eines geladenen Ereignisses</span><span class="sxs-lookup"><span data-stu-id="0c974-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="0c974-103">Dieses Beispiel zeigt, wie behandelt die <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> Ereignis und einem entsprechenden Szenario für die Behandlung dieses Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="0c974-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="0c974-104">Der Ereignishandler erstellt ein <xref:System.Windows.Controls.Button> beim Laden der Seite.</span><span class="sxs-lookup"><span data-stu-id="0c974-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c974-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c974-105">Example</span></span>  
 <span data-ttu-id="0c974-106">Im folgenden Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zusammen mit einem Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="0c974-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="0c974-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c974-107">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="0c974-108">Objektlebensdauer-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0c974-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="0c974-109">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="0c974-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="0c974-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0c974-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
