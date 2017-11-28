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
# <a name="how-to-change-the-cursor-type"></a>Gewusst wie: Ändern des Cursortyps
In diesem Beispiel wird gezeigt, wie so ändern Sie die <xref:System.Windows.Input.Cursor> des Mauszeigers für ein bestimmtes Element und für die Anwendung.  
  
 In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei- und eine CodeBehind-Datei.  
  
## <a name="example"></a>Beispiel  
 Die Benutzeroberfläche erstellt wird, besteht aus dem eine <xref:System.Windows.Controls.ComboBox> , wählen Sie die gewünschte <xref:System.Windows.Input.Cursor>, ein Paar von <xref:System.Windows.Controls.RadioButton> Objekte, um festzustellen, ob die Cursor Änderung nur ein einzelnes Element betrifft oder für die gesamte Anwendung gilt, und ein <xref:System.Windows.Controls.Border> Hierbei handelt es sich um das Element, dem der neue Cursor angewendet wird.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Hinter der folgende Code erstellt ein <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> -Ereignishandler, der aufgerufen wird, wenn sich der Cursortyp geändert wird, in der <xref:System.Windows.Controls.ComboBox>.  Eine Switch-Anweisung filtert, auf den Cursornamen und legt die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft auf die <xref:System.Windows.Controls.Border> die Bezeichnung *DisplayArea*.  
  
 Wenn der Cursor auf "Gesamte Anwendung" Changeset wird die <xref:System.Windows.Input.Mouse.OverrideCursor%2A> -Eigenschaftensatz auf die <xref:System.Windows.FrameworkElement.Cursor%2A> Eigenschaft von der <xref:System.Windows.Controls.Border> Steuerelement.  Dies zwingt den Cursor für die gesamte Anwendung ändern.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
