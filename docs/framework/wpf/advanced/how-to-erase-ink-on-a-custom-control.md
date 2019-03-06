---
title: 'Vorgehensweise: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365892"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Vorgehensweise: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement
Die <xref:System.Windows.Ink.IncrementalStrokeHitTester> bestimmt, ob die derzeit gezogene Strich einer anderen Strich überschneidet.  Dies ist nützlich für ein Steuerelement erstellen, die einen Benutzer Teile eines Strichs löschen kann, wie ein Benutzer kann auf eine <xref:System.Windows.Controls.InkCanvas> bei der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein benutzerdefiniertes Steuerelement, das dem Benutzer ermöglicht, die Teile von Strichen löschen.  Dieses Beispiel erstellt ein Steuerelement, das Freihandeingabe enthält, wenn es initialisiert wird.  Um ein Steuerelement erstellen, die Freihandeingaben erfasst werden, finden Sie unter [erstellen ein Steuerelement für Freihandeingaben](creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
