---
title: 'Gewusst wie: Positionieren eines benutzerdefinierten Kontextmenüs in einem "RichTextBox"-Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: bde28cdb87bdaef3198d1efd3059fed3d0ae0ce2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553850"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="7e249-102">Gewusst wie: Positionieren eines benutzerdefinierten Kontextmenüs in einem "RichTextBox"-Element</span><span class="sxs-lookup"><span data-stu-id="7e249-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="7e249-103">In diesem Beispiel wird gezeigt, wie zum Positionieren eines benutzerdefinierten Kontextmenüs für eine <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7e249-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="7e249-104">Bei der Implementierung eines benutzerdefinierten Kontextmenüs für ein **RichTextBox**-Element sind Sie verantwortlich für die Positionierung des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="7e249-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="7e249-105">Standardmäßig wird ein benutzerdefiniertes Kontextmenü in der Mitte des **RichTextBox**-Elements geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7e249-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e249-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e249-106">Example</span></span>  
 <span data-ttu-id="7e249-107">Um das Standardverhalten für die Platzierung außer Kraft setzen, fügen Sie einen Listener für die <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="7e249-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="7e249-108">Im folgenden Beispiel wird veranschaulicht, wie dies programmgesteuert erfolgt.</span><span class="sxs-lookup"><span data-stu-id="7e249-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="7e249-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e249-109">Example</span></span>  
 <span data-ttu-id="7e249-110">Das folgende Beispiel zeigt einer Implementierung der entsprechenden <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignislistener.</span><span class="sxs-lookup"><span data-stu-id="7e249-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="7e249-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e249-111">See Also</span></span>  
 [<span data-ttu-id="7e249-112">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7e249-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="7e249-113">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="7e249-113">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
