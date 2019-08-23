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
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962188"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Übersicht über die ContextMenu-Komponente (Windows Forms)
> [!IMPORTANT]
> Obwohl <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenuStrip> die-und- <xref:System.Windows.Forms.ContextMenu> Steuerelemente früherer Versionen ersetzen und Funktionen hinzu <xref:System.Windows.Forms.MainMenu> fügen <xref:System.Windows.Forms.ContextMenu> , werden Sie sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.  
  
 Mit der Windows Forms <xref:System.Windows.Forms.ContextMenu> -Komponente können Sie Benutzern ein leicht zugängliches Kontextmenü mit häufig verwendeten Befehlen bereitstellen, die dem ausgewählten Objekt zugeordnet sind. Die Elemente in einem Kontextmenü sind häufig eine Teilmenge der Elemente aus den Hauptmenüs, die an anderer Stelle in der Anwendung angezeigt werden. Benutzer können in der Regel auf ein Kontextmenü zugreifen, indem Sie mit der rechten Maustaste auf die Maus klicken. Auf Windows Forms werden Kontextmenüs Steuerelementen zugeordnet.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Sie können ein Kontextmenü einem-Steuerelement zuordnen, indem Sie die <xref:System.Windows.Forms.Control.ContextMenu%2A> -Eigenschaft des <xref:System.Windows.Forms.ContextMenu> -Steuer Elements auf die-Komponente festlegen. Einem einzelnen Kontextmenü können mehrere Steuerelemente zugeordnet werden, aber jedes Steuerelement kann nur über ein Kontextmenü verfügen.  
  
 Die Schlüsseleigenschaft der <xref:System.Windows.Forms.ContextMenu> Komponente ist die <xref:System.Windows.Forms.Menu.MenuItems%2A> -Eigenschaft. Sie können Menü Elemente hinzufügen, indem Sie <xref:System.Windows.Forms.MenuItem> Objekte Programm gesteuert erstellen und Sie <xref:System.Windows.Forms.Menu.MenuItemCollection> dem Kontextmenü hinzufügen. Da die Elemente in einem Kontextmenü in der Regel aus anderen Menüs gezeichnet werden, fügen Sie Elemente häufig zu einem Kontextmenü hinzu, indem Sie Sie kopieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
