---
title: "Übersicht über die MainMenu-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f5cfe3a97bbbd4d5ba2d3ba089736599b6a2190
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mainmenu-component-overview-windows-forms"></a>Übersicht über die MainMenu-Komponente (Windows Forms)
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzt und funktionell die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente von früheren Versionen <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> für Abwärtskompatibilität und für zukünftige Verwendung beibehalten werden, falls gewünscht.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> Komponente wird ein Menü angezeigt, zur Laufzeit. Alle Untermenüs des Hauptmenüs und einzelne Elemente sind <xref:System.Windows.Forms.MenuItem> Objekte.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Ein Menüelement kann als das Standardelement gekennzeichnet werden, durch Festlegen der <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> Eigenschaft `true`. Das Standardelement wird in Fettschrift angezeigt, wenn das Menü geklickt wird. Des Menüelements <xref:System.Windows.Forms.MenuItem.Checked%2A> Eigenschaft `true` oder `false`, und gibt an, ob das Menüelement aktiviert ist. Des Menüelements <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Eigenschaft passt die Anzeige des ausgewählten Elements: Wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> festgelegt ist, um `true`, ein Optionsfeld wird neben dem Element angezeigt, wenn <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> auf festgelegt ist `false`, ein Häkchen neben dem Element angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [Übersicht über das MenuStrip-Steuerelement](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
