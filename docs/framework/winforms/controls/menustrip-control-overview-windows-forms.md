---
title: Übersicht über das MenuStrip-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761366"
---
# <a name="menustrip-control-overview-windows-forms"></a>Übersicht über das MenuStrip-Steuerelement (Windows Forms)
Menüs stellen die Funktionalität für Ihre Benutzer von Befehlen, die von einem gemeinsamen Thema zusammengefasst sind.  
  
 Die <xref:System.Windows.Forms.MenuStrip> Steuerelement ist in dieser Version von Visual Studio und .NET Framework neu. Mit dem Steuerelement können Sie problemlos Menüs wie in Microsoft Office erstellen.  
  
 Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement unterstützt die Multiple Document Interface (MDI) und das Zusammenführen von Menüs, QuickInfos und Überlauf. Sie können die benutzerfreundlichkeit und die Lesbarkeit des Menüs durch Hinzufügen der Zugriffsschlüssel, Tastenkombinationen, Häkchen, Bildern und Trennlinien verbessern.  
  
 Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement ersetzt und funktionell erweitert die <xref:System.Windows.Forms.MainMenu> steuern; allerdings die <xref:System.Windows.Forms.MainMenu> Steuerelement wird für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, falls gewünscht.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Möglichkeiten, das MenuStrip-Steuerelement zu verwenden.  
 Verwenden der <xref:System.Windows.Forms.MenuStrip> zu steuern:  
  
- Erstellen Sie ganz einfach benutzerdefinierte, häufig verwendete Menüs, die unterstützen erweiterte Benutzer Schnittstelle und das Layout-Funktionen, z. B. Text und Bild Sortierung und Ausrichtung, Drag & Drop-Vorgänge, MDI, Überlauf und alternative Modi für den Zugriff auf Befehle im Menü.  
  
- Unterstützt das typische Aussehen und Verhalten des Betriebssystems.  
  
- Behandeln von Ereignissen konsistent für alle Container und enthaltene Elemente, auf die gleiche Weise, die Sie behandeln Ereignisse für andere Steuerelemente.  
  
 Die folgende Tabelle zeigt einige besonders wichtigen Eigenschaften der <xref:System.Windows.Forms.MenuStrip> und die zugehörigen Klassen.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ruft ab oder legt die <xref:System.Windows.Forms.ToolStripMenuItem> , die zum Anzeigen einer Liste von untergeordneten MDI-Formularen verwendet wird.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ruft ab oder legt sie fest, wie untergeordnete Menüs mit übergeordneten Menüs in MDI-Anwendungen zusammengeführt werden.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Übernimmt oder bestimmt die Position eines zusammengeführten Elements in einem Menü in MDI-Anwendungen.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ruft ab oder legt einen Wert, der angibt, ob das Formular ein Container für untergeordnete MDI-Formulare ist.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ruft ab oder legt einen Wert, der angibt, ob QuickInfos, für angezeigt werden die <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.MenuStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Übernimmt oder bestimmt die zugeordneten Tastenkombinationen der <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ruft ab oder legt ein Wert, der angibt, ob die Tastenkombinationen, zugeordnet sind die <xref:System.Windows.Forms.ToolStripMenuItem> neben der <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 Die folgende Tabelle zeigt die wichtigen <xref:System.Windows.Forms.MenuStrip> Assistentenklassen.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Stellt eine auswählbare Option angezeigt, die auf eine <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Stellt ein Kontextmenü dar.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Stellt ein Steuerelement, mit dem Benutzer um ein einzelnes Element aus einer Liste auszuwählen, die angezeigt wird, wenn der Benutzer klickt, ein <xref:System.Windows.Forms.ToolStripDropDownButton> eines Menüelements auf höherer Ebene.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Stellt grundlegende Funktionen für Steuerelemente abgeleitet <xref:System.Windows.Forms.ToolStripItem> , Dropdown-Elemente beim Klicken auf anzeigen.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
