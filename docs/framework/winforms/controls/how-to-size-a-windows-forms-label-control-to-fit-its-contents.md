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
ms.workload: dotnet
ms.openlocfilehash: a2c34506ca33af80b83f365893e56a5a9d437b89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
