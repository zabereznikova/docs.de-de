---
title: "Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd89d72264e5837d2c41fcb0ab024a7b16f4205b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Gewusst wie: Anpassen der Größe des Label-Steuerelements in Windows Forms an seinen Inhalt
Windows Forms <xref:System.Windows.Forms.Label> Steuerelement kann es sich um einzeilige oder mehrzeilige und können werden entweder eine feste Größe oder können automatisch ändern, ihre Beschriftung angepasst. Die <xref:System.Windows.Forms.Label.AutoSize%2A> -Eigenschaft hilft Ihnen bei der Steuerelemente größere oder kleinere Beschriftungen, Anpassen der ist besonders nützlich, wenn sich die Beschriftung zur Laufzeit ändert.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Um ein Bezeichnungsfeld-Steuerelement dynamisch angepasst seinen Inhalt zu machen.  
  
1.  Legen Sie dessen <xref:System.Windows.Forms.Label.AutoSize%2A> Eigenschaft `true`.  
  
 Wenn <xref:System.Windows.Forms.Label.AutoSize%2A> auf festgelegt ist `false`, den angegebenen Wörtern in der <xref:System.Windows.Forms.Label.Text%2A> Eigenschaft nach Möglichkeit die nächste Zeile umbrochen, aber das Steuerelement wird nicht vergrößert.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen von Zugriffstasten mit Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Übersicht über das Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Label-Steuerelement](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
