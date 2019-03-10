---
title: 'Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: e1d7917d7e12ba286e7ddf4e95a68769852a17f7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704335"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Vorgehensweise: Aktivieren Sie die TAB-Taste zum Verlassen eines ToolStrip-Steuerelements
Verwenden Sie das folgende Verfahren, um dem Benutzer ermöglichen, die TAB-Taste zum Verschieben von einer <xref:System.Windows.Forms.ToolStrip> auf das nächste Steuerelement in der Aktivierreihenfolge.  
  
 Die <xref:System.Windows.Forms.ToolStrip> akzeptiert das erste Drücken der TAB-Taste und der Pfeil Schlüssel wählen Elemente in der <xref:System.Windows.Forms.ToolStrip>. Wenn der Benutzer ein zweites Mal die TAB-Taste drückt, dauert es den Benutzer das nächste Steuerelement in der Aktivierreihenfolge.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Um dem Benutzer die TAB-Taste zum Verlassen eines ToolStrip zum nächsten Steuerelement zu aktivieren.  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.TabStop%2A> Eigenschaft der <xref:System.Windows.Forms.ToolStrip> zu `true`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
