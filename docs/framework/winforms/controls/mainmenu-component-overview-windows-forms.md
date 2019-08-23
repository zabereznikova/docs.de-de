---
title: Übersicht über die MainMenu-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952131"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Übersicht über die MainMenu-Komponente (Windows Forms)
> [!IMPORTANT]
> Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.  
  
 Die Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente zeigt ein Menü zur Laufzeit an. Alle Untermenüs des Hauptmenüs und der einzelnen Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Ein Menü Element kann als Standardelement festgelegt werden, indem die <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> -Eigenschaft `true`auf festgelegt wird. Das Standardelement wird in fettem Text angezeigt, wenn auf das Menü geklickt wird. Die- <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft des Menü Elements ist `true` entweder `false`oder und gibt an, ob das Menü Element ausgewählt ist. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Die-Eigenschaft des Menü Elements passt die Darstellung des ausgewählten Elements an: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `true`festgelegt ist, wird neben dem Element ein Optionsfeld angezeigt. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> wenn auf `false`festgelegt ist, wird neben dem Element ein Häkchen angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
