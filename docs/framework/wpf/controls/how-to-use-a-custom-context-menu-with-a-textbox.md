---
title: 'Vorgehensweise: Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 805f5205a91f9b3da0c48c987f1f49f1d81892b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358599"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="1ab12-102">Vorgehensweise: Verwenden eines benutzerdefinierten Kontextmenüs mit "TextBox"</span><span class="sxs-lookup"><span data-stu-id="1ab12-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="1ab12-103">Dieses Beispiel zeigt, wie Sie definieren und Implementieren eines einfachen benutzerdefinierten Kontextmenüs für ein <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1ab12-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ab12-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ab12-104">Example</span></span>  
 <span data-ttu-id="1ab12-105">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiel definiert eine <xref:System.Windows.Controls.TextBox> -Steuerelement, das ein benutzerdefiniertes Kontextmenü enthält.</span><span class="sxs-lookup"><span data-stu-id="1ab12-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="1ab12-106">Das Kontextmenü wird definiert, mit einem <xref:System.Windows.Controls.ContextMenu> Element.</span><span class="sxs-lookup"><span data-stu-id="1ab12-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="1ab12-107">Das Kontextmenü selbst besteht aus einer Reihe von <xref:System.Windows.Controls.MenuItem> Elemente und <xref:System.Windows.Controls.Separator> Elemente.</span><span class="sxs-lookup"><span data-stu-id="1ab12-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="1ab12-108">Jede <xref:System.Windows.Controls.MenuItem> Element definiert einen Befehl im Kontextmenü; die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Attribut definiert den Anzeigetext für den Menübefehl, und die <xref:System.Windows.Controls.MenuItem.Click> Attribut gibt an, eine Handlermethode, die für jedes Menüelement im.</span><span class="sxs-lookup"><span data-stu-id="1ab12-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="1ab12-109">Die <xref:System.Windows.Controls.Separator> Element wird einfach eine Trennung Zeile zwischen den Menüelementen der vorherigen und nachfolgenden gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ab12-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="1ab12-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ab12-110">Example</span></span>  
 <span data-ttu-id="1ab12-111">Das folgende Beispiel zeigt den Implementierungscode für den vorherigen Kontextmenüdefinition sowie den Code, der aktiviert und im Kontextmenü deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1ab12-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="1ab12-112">Die <xref:System.Windows.Controls.ContextMenu.Opened> Ereignis wird verwendet, um dynamisch aktivieren oder deaktivieren je nach den aktuellen Status der bestimmten Befehle die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1ab12-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="1ab12-113">Verwenden Sie zum Wiederherstellen der standardmäßigen Kontextmenü der <xref:System.Windows.DependencyObject.ClearValue%2A> Methode zum Löschen des Werts, der die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1ab12-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="1ab12-114">Um das Kontextmenü vollständig zu deaktivieren, legen die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft einen null-Verweis (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="1ab12-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="1ab12-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ab12-115">See also</span></span>
- [<span data-ttu-id="1ab12-116">Verwenden der Rechtschreibprüfung mit einem Kontextmenü</span><span class="sxs-lookup"><span data-stu-id="1ab12-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="1ab12-117">Übersicht über TextBox</span><span class="sxs-lookup"><span data-stu-id="1ab12-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="1ab12-118">Übersicht über RichTextBox</span><span class="sxs-lookup"><span data-stu-id="1ab12-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
