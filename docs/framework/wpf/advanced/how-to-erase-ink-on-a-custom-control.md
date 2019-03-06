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
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="18a60-102">Vorgehensweise: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="18a60-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="18a60-103">Die <xref:System.Windows.Ink.IncrementalStrokeHitTester> bestimmt, ob die derzeit gezogene Strich einer anderen Strich überschneidet.</span><span class="sxs-lookup"><span data-stu-id="18a60-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="18a60-104">Dies ist nützlich für ein Steuerelement erstellen, die einen Benutzer Teile eines Strichs löschen kann, wie ein Benutzer kann auf eine <xref:System.Windows.Controls.InkCanvas> bei der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> nastaven NA hodnotu <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span><span class="sxs-lookup"><span data-stu-id="18a60-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18a60-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18a60-105">Example</span></span>  
 <span data-ttu-id="18a60-106">Das folgende Beispiel erstellt ein benutzerdefiniertes Steuerelement, das dem Benutzer ermöglicht, die Teile von Strichen löschen.</span><span class="sxs-lookup"><span data-stu-id="18a60-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="18a60-107">Dieses Beispiel erstellt ein Steuerelement, das Freihandeingabe enthält, wenn es initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="18a60-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="18a60-108">Um ein Steuerelement erstellen, die Freihandeingaben erfasst werden, finden Sie unter [erstellen ein Steuerelement für Freihandeingaben](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="18a60-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
