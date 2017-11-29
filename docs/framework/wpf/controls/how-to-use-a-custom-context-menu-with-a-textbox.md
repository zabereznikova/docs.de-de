---
title: "Gewusst wie: Verwenden eines benutzerdefinierten Kontextmenüs mit \"TextBox\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc2bb5645467e785626ad8e2a4624335d5d110fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="cca27-102">Gewusst wie: Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"</span><span class="sxs-lookup"><span data-stu-id="cca27-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="cca27-103">In diesem Beispiel wird gezeigt, wie definieren und Implementieren eines einfachen benutzerdefinierten Kontextmenüs für eine <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="cca27-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca27-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cca27-104">Example</span></span>  
 <span data-ttu-id="cca27-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel definiert eine <xref:System.Windows.Controls.TextBox> -Steuerelement, ein benutzerdefiniertes Kontextmenü enthält.</span><span class="sxs-lookup"><span data-stu-id="cca27-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="cca27-106">Das Kontextmenü wird definiert, mit einem <xref:System.Windows.Controls.ContextMenu> Element.</span><span class="sxs-lookup"><span data-stu-id="cca27-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="cca27-107">Im Kontextmenü den Befehl selbst besteht aus einer Reihe von <xref:System.Windows.Controls.MenuItem> Elemente und <xref:System.Windows.Controls.Separator> Elemente.</span><span class="sxs-lookup"><span data-stu-id="cca27-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="cca27-108">Jede <xref:System.Windows.Controls.MenuItem> Element definiert einen Befehl im Kontextmenü; der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Attribut definiert den Anzeigetext für den Menübefehl und die <xref:System.Windows.Controls.MenuItem.Click> Attribut gibt eine Handlermethode für jedes Menüelement an.</span><span class="sxs-lookup"><span data-stu-id="cca27-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="cca27-109">Die <xref:System.Windows.Controls.Separator> Element einfach führt dazu, dass eine Trennung Linie zwischen dem vorherigen und dem nachfolgenden Menüelement gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cca27-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="cca27-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cca27-110">Example</span></span>  
 <span data-ttu-id="cca27-111">Das folgende Beispiel zeigt den Implementierungscode für den vorherigen Kontextmenüdefinition sowie den Code, der aktiviert und deaktiviert das Kontextmenü an.</span><span class="sxs-lookup"><span data-stu-id="cca27-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="cca27-112">Die <xref:System.Windows.Controls.ContextMenu.Opened> Ereignis wird verwendet, um dynamisch aktivieren oder deaktivieren bestimmte Befehle abhängig von den aktuellen Status des der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="cca27-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="cca27-113">Verwenden Sie zum Wiederherstellen des standardmäßigen Kontextmenüs der <xref:System.Windows.DependencyObject.ClearValue%2A> Methode, um den Wert der Löschen der <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cca27-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="cca27-114">Um das Kontextmenü vollständig zu deaktivieren, legen die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft auf einen null-Verweis (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cca27-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="cca27-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cca27-115">See Also</span></span>  
 [<span data-ttu-id="cca27-116">Verwenden der Rechtschreibprüfung mit einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="cca27-116">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="cca27-117">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="cca27-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="cca27-118">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="cca27-118">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
