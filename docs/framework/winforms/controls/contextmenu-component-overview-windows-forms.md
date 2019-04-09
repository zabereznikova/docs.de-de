---
title: Übersicht über die ContextMenu-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 2acbcc9197a630a993471c22e572a4f3ed682c64
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090562"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Übersicht über die ContextMenu-Komponente (Windows Forms)
> [!IMPORTANT]
>  Obwohl <xref:System.Windows.Forms.MenuStrip> und <xref:System.Windows.Forms.ContextMenuStrip> ersetzen und Erweitern der Funktionalität für die <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> Steuerelemente aus früheren Versionen, <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu> werden für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, wenn Sie auswählen.  
  
 Mit der Windows Forms <xref:System.Windows.Forms.ContextMenu> Komponente Sie bereitstellen, Benutzern ein leicht zugängliches Kontextmenü mit häufig verwendeten Befehlen, die dem ausgewählten Objekt zugeordnet sind. Die Elemente in einem Kontextmenü sind häufig eine Teilmenge der Elemente aus den Hauptmenüs, die an anderer Stelle in der Anwendung angezeigt werden. Ein Benutzer kann ein Kontextmenü mit der rechten Maustaste in der Maustaste in der Regel zugreifen. In Windows Forms sind die Kontextmenüs Steuerelementen zugeordnet.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Sie können ein Kontextmenü mit einem Steuerelement zuordnen, durch Festlegen des Steuerelements <xref:System.Windows.Forms.Control.ContextMenu%2A> Eigenschaft, um die <xref:System.Windows.Forms.ContextMenu> Komponente. Ein Kontextmenü für die einzelnen kann mit mehreren Steuerelementen verbunden werden, aber jedes Steuerelement kann nur ein Kontextmenü haben.  
  
 Die wichtigste Eigenschaft die <xref:System.Windows.Forms.ContextMenu> Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A> Eigenschaft. Sie können Menüelemente hinzufügen, indem Sie programmgesteuert erstellen <xref:System.Windows.Forms.MenuItem> Objekte und Hinzufügen der <xref:System.Windows.Forms.Menu.MenuItemCollection> des Kontextmenüs. Da die Elemente in einem Kontextmenü in der Regel aus anderen Menüs gezeichnet werden, werden Sie am häufigsten Elemente in einem Kontextmenü Menüelemente hinzufügen, durch Kopieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
