---
title: 'Vorgehensweise: Ändern des Cursortyps'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 5c9e6931f6addb62a51e44b06a159d4e7b1e5f8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776674"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="71591-102">Vorgehensweise: Ändern des Cursortyps</span><span class="sxs-lookup"><span data-stu-id="71591-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="71591-103">Dieses Beispiel zeigt, wie Sie ändern die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element, und für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="71591-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="71591-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="71591-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71591-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71591-105">Example</span></span>  
 <span data-ttu-id="71591-106">Die Benutzeroberfläche wird erstellt, die besteht aus einer <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> zu bestimmen, ob die Cursor Änderung für nur ein einzelnes Element gilt oder für die gesamte Anwendung gilt Objekte und eine <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem auf der neue Cursor angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="71591-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="71591-107">Hinter der folgende Code erstellt eine <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn der Cursortyp, in geändert wurde der <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="71591-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="71591-108">Eine Switch-Anweisung filtert auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft für die <xref:System.Windows.Controls.Border> mit dem Namen *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="71591-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="71591-109">Wenn die Änderung der Cursor auf "Gesamte Anwendung" festgelegt ist die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft der <xref:System.Windows.Controls.Border> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="71591-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="71591-110">Dies zwingt den Cursor für die gesamte Anwendung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="71591-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="71591-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71591-111">See also</span></span>

- [<span data-ttu-id="71591-112">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="71591-112">Input Overview</span></span>](input-overview.md)
