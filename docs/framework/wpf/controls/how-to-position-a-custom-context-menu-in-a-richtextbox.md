---
title: 'Vorgehensweise: Positionieren eines benutzerdefinierten Kontextmenüs in einer RichTextBox'
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
ms.openlocfilehash: abb5bbb5d5a537b14f334782e87fa7caf0c7976f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367875"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="12a88-102">Vorgehensweise: Positionieren eines benutzerdefinierten Kontextmenüs in einer RichTextBox</span><span class="sxs-lookup"><span data-stu-id="12a88-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="12a88-103">Dieses Beispiel zeigt das Positionieren eines benutzerdefinierten Kontextmenüs für ein <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="12a88-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="12a88-104">Bei der Implementierung eines benutzerdefinierten Kontextmenüs für ein **RichTextBox**-Element sind Sie verantwortlich für die Positionierung des Kontextmenüs.</span><span class="sxs-lookup"><span data-stu-id="12a88-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="12a88-105">Standardmäßig wird ein benutzerdefiniertes Kontextmenü in der Mitte des **RichTextBox**-Elements geöffnet.</span><span class="sxs-lookup"><span data-stu-id="12a88-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12a88-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12a88-106">Example</span></span>  
 <span data-ttu-id="12a88-107">Um das standardpositionierungsverhalten außer Kraft setzen, fügen Sie einen Listener für die <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="12a88-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="12a88-108">Im folgenden Beispiel wird veranschaulicht, wie dies programmgesteuert erfolgt.</span><span class="sxs-lookup"><span data-stu-id="12a88-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="12a88-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12a88-109">Example</span></span>  
 <span data-ttu-id="12a88-110">Das folgende Beispiel zeigt einer Implementierung der entsprechenden <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> Ereignislistener.</span><span class="sxs-lookup"><span data-stu-id="12a88-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="12a88-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12a88-111">See also</span></span>
- [<span data-ttu-id="12a88-112">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="12a88-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="12a88-113">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="12a88-113">TextBox Overview</span></span>](textbox-overview.md)
