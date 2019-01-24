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
ms.openlocfilehash: 529b57ed443791b87331358a7e6c420dd63933a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700623"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Übersicht über die MainMenu-Komponente (Windows Forms)
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.  
  
 Die Windows-Formulare <xref:System.Windows.Forms.MainMenu> Komponente wird ein Menü zur Laufzeit angezeigt. Alle Untermenüs des Hauptmenüs und einzelne Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Ein Menüelement kann als das Standardelement gekennzeichnet werden, durch Festlegen der <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> Eigenschaft `true`. Das Standardelement in Fettdruck angezeigt wird, wenn Sie im Menü geklickt wird. Des Menüelements <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft `true` oder `false`, und gibt an, ob das Menüelement ausgewählt ist. Des Menüelements <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Eigenschaft passt die Anzeige des ausgewählten Elements: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> nastaven NA hodnotu `true`, ein Optionsfeld wird neben dem Element; angezeigt, wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> nastaven NA hodnotu `false`, ein Häkchen neben dem Element angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
