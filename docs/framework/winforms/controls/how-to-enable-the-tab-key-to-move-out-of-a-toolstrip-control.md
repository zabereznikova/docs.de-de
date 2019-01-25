---
title: 'Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663070"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements
Verwenden Sie das folgende Verfahren, um dem Benutzer ermöglichen, die TAB-Taste zum Verschieben von einer <xref:System.Windows.Forms.ToolStrip> auf das nächste Steuerelement in der Aktivierreihenfolge.  
  
 Die <xref:System.Windows.Forms.ToolStrip> akzeptiert das erste Drücken der TAB-Taste und der Pfeil Schlüssel wählen Elemente in der <xref:System.Windows.Forms.ToolStrip>. Wenn der Benutzer ein zweites Mal die TAB-Taste drückt, dauert es den Benutzer das nächste Steuerelement in der Aktivierreihenfolge.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Um dem Benutzer die TAB-Taste zum Verlassen eines ToolStrip zum nächsten Steuerelement zu aktivieren.  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.TabStop%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStrip> zu `true`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
