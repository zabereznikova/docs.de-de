---
title: 'Gewusst wie: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 66c0d19b368b56821fd4034ec4c7cd397b244ab0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543246"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Gewusst wie: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement
Die <xref:System.Windows.Ink.IncrementalStrokeHitTester> bestimmt, ob die aktuell gezeichnete Strich mit einer anderen Strich überschneidet.  Dies ist hilfreich, für die Erstellung eines Steuerelements, den Benutzer Teile eines Strichs löschen kann, wie ein Benutzer kann auf eine <xref:System.Windows.Controls.InkCanvas> bei der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> festgelegt ist, um <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein benutzerdefiniertes Steuerelement, das dem Benutzer ermöglicht, die Teile von Strichen löschen.  Dieses Beispiel erstellt ein Steuerelement, das Freihandeingaben enthält, wenn es initialisiert wird.  Zur Erstellung eines Steuerelements, das Freihandeingaben erfasst, finden Sie unter [Erstellen eines Steuerelements der Freihand-Eingabe](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
