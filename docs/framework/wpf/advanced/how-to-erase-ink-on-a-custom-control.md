---
title: "Gewusst wie: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement"
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
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e05163bcbafd360e0929fe784ff1111bd0663ef3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>Gewusst wie: Löschen von Freihandeingaben auf einem benutzerdefinierten Steuerelement
Die <xref:System.Windows.Ink.IncrementalStrokeHitTester> bestimmt, ob die aktuell gezeichnete Strich mit einer anderen Strich überschneidet.  Dies ist hilfreich, für die Erstellung eines Steuerelements, den Benutzer Teile eines Strichs löschen kann, wie ein Benutzer kann auf eine <xref:System.Windows.Controls.InkCanvas> bei der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> festgelegt ist, um <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein benutzerdefiniertes Steuerelement, das dem Benutzer ermöglicht, die Teile von Strichen löschen.  Dieses Beispiel erstellt ein Steuerelement, das Freihandeingaben enthält, wenn es initialisiert wird.  Zur Erstellung eines Steuerelements, das Freihandeingaben erfasst, finden Sie unter [Erstellen eines Steuerelements der Freihand-Eingabe](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
