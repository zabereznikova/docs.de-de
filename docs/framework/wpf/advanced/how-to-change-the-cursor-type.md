---
title: "Gewusst wie: Ändern des Cursortyps"
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
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41cd8c9cd647c7efbc4e6cf13517ed638245e51c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="f302e-102">Gewusst wie: Ändern des Cursortyps</span><span class="sxs-lookup"><span data-stu-id="f302e-102">How to: Change the Cursor Type</span></span>
<span data-ttu-id="f302e-103">In diesem Beispiel wird gezeigt, wie so ändern Sie die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f302e-103">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="f302e-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei- und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="f302e-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f302e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f302e-105">Example</span></span>  
 <span data-ttu-id="f302e-106">Die Benutzeroberfläche erstellt wird, besteht aus dem eine <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> Objekte, um festzustellen, ob die Cursor Änderung nur ein einzelnes Element betrifft oder für die gesamte Anwendung gilt, und ein <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem der neue Cursor angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f302e-106">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="f302e-107">Hinter der folgende Code erstellt ein <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn sich der Cursortyp geändert wird, in der <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="f302e-107">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="f302e-108">Eine Switch-Anweisung filtert, auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft auf die <xref:System.Windows.Controls.Border> die Bezeichnung *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="f302e-108">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="f302e-109">Wenn der Cursor auf "Gesamte Anwendung" Changeset wird die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft von der <xref:System.Windows.Controls.Border> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f302e-109">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="f302e-110">Dies zwingt den Cursor für die gesamte Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="f302e-110">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="f302e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f302e-111">See Also</span></span>  
 [<span data-ttu-id="f302e-112">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="f302e-112">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
