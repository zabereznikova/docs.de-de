---
title: 'Gewusst wie: Ändern des Cursortyps'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 26fc2584381307612c40b615f169902089d9d1f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543392"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="2e5da-102">Gewusst wie: Ändern des Cursortyps</span><span class="sxs-lookup"><span data-stu-id="2e5da-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="2e5da-103">In diesem Beispiel wird gezeigt, wie so ändern Sie die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2e5da-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="2e5da-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei- und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="2e5da-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e5da-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e5da-105">Example</span></span>  
 <span data-ttu-id="2e5da-106">Die Benutzeroberfläche erstellt wird, besteht aus dem eine <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> Objekte, um festzustellen, ob die Cursor Änderung nur ein einzelnes Element betrifft oder für die gesamte Anwendung gilt, und ein <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem der neue Cursor angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e5da-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="2e5da-107">Hinter der folgende Code erstellt ein <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn sich der Cursortyp geändert wird, in der <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="2e5da-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="2e5da-108">Eine Switch-Anweisung filtert, auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft auf die <xref:System.Windows.Controls.Border> die Bezeichnung *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="2e5da-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="2e5da-109">Wenn der Cursor auf "Gesamte Anwendung" Changeset wird die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft von der <xref:System.Windows.Controls.Border> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2e5da-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="2e5da-110">Dies zwingt den Cursor für die gesamte Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="2e5da-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="2e5da-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e5da-111">See Also</span></span>  
 [<span data-ttu-id="2e5da-112">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="2e5da-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
