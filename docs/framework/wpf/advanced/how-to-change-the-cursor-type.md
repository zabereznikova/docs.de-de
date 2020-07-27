---
title: 'Gewusst wie: Ändern des Cursortyps'
description: Ändern Sie den Mauszeiger Cursor für ein Element und für eine Anwendung in Windows Presentation Foundation. Dieses Beispiel besteht aus XAML und einer Code Behind-Datei.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165960"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="c3a27-104">Gewusst wie: Ändern des Cursortyps</span><span class="sxs-lookup"><span data-stu-id="c3a27-104">How to: Change the Cursor Type</span></span>
<span data-ttu-id="c3a27-105">In diesem Beispiel wird gezeigt, wie der <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c3a27-105">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="c3a27-106">Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei und einer Code Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="c3a27-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3a27-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3a27-107">Example</span></span>  
 <span data-ttu-id="c3a27-108">Die Benutzeroberfläche wird erstellt. Diese besteht aus einem <xref:System.Windows.Controls.ComboBox> zum Auswählen der gewünschten <xref:System.Windows.Input.Cursor> , einem Paar von- <xref:System.Windows.Controls.RadioButton> Objekten, um zu bestimmen, ob die Cursor Änderung nur auf ein einzelnes Element angewendet wird oder auf die gesamte Anwendung angewendet wird, und ein-Element, auf das das Element angewendet wird, auf das <xref:System.Windows.Controls.Border> der neue Cursor angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3a27-108">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="c3a27-109">Der folgende Code Behind erstellt einen- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> Ereignishandler, der aufgerufen wird, wenn der Cursortyp in geändert wird <xref:System.Windows.Controls.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="c3a27-109">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="c3a27-110">Eine Switch-Anweisung filtert nach dem Cursor Namen und legt die- <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft auf dem-Objekt fest <xref:System.Windows.Controls.Border> , das den Namen *DisplayArea*hat.</span><span class="sxs-lookup"><span data-stu-id="c3a27-110">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="c3a27-111">Wenn die Cursor Änderung auf "gesamte Anwendung" festgelegt ist, <xref:System.Windows.Input.Mouse.OverrideCursor%2A> wird die-Eigenschaft auf die-Eigenschaft des-Steuer Elements festgelegt <xref:System.Windows.FrameworkElement.Cursor%2A> <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="c3a27-111">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="c3a27-112">Dadurch wird erzwungen, dass der Cursor für die gesamte Anwendung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="c3a27-112">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="c3a27-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3a27-113">See also</span></span>

- [<span data-ttu-id="c3a27-114">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="c3a27-114">Input Overview</span></span>](input-overview.md)
