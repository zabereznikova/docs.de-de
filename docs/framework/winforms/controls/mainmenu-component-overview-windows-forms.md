---
title: Übersicht über die MainMenu-Komponente
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745118"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Übersicht über die MainMenu-Komponente (Windows Forms)
> [!IMPORTANT]
> Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> die-<xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>-Steuerelemente früherer Versionen ersetzen und Funktionen hinzufügen, werden <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> sowohl für Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten.  
  
 Die Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente zeigt ein Menü zur Laufzeit an. Alle Untermenüs des Hauptmenüs und der einzelnen Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Ein Menü Element kann als Standardelement festgelegt werden, indem die <xref:System.Windows.Forms.MenuItem.DefaultItem%2A>-Eigenschaft auf `true`festgelegt wird. Das Standardelement wird in fettem Text angezeigt, wenn auf das Menü geklickt wird. Die <xref:System.Windows.Forms.MenuItem.Checked%2A>-Eigenschaft des Menü Elements ist entweder `true` oder `false`und gibt an, ob das Menü Element ausgewählt ist. Die <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>-Eigenschaft des Menü Elements passt die Darstellung des ausgewählten Elements an: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `true`festgelegt ist, wird neben dem Element ein Optionsfeld angezeigt. Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf `false`festgelegt ist, wird neben dem Element ein Häkchen angezeigt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Übersicht über das MenuStrip-Steuerelement](menustrip-control-overview-windows-forms.md)
