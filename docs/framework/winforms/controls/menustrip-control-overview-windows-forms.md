---
title: Übersicht über das MenuStrip-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: b09d653210c72a38bbc4dc0858ae2553ad9cbeef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="menustrip-control-overview-windows-forms"></a>Übersicht über das MenuStrip-Steuerelement (Windows Forms)
Menüs Funktionalität verfügbar machen, die Benutzern von Befehlen, die durch eine allgemeine Thematik gruppiert werden.  
  
 Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement ist in dieser Version von Visual Studio und .NET Framework neu. Mit dem Steuerelement können Sie problemlos Menüs wie in Microsoft Office erstellen.  
  
 Die <xref:System.Windows.Forms.MenuStrip> Steuerelement unterstützt, die Multiple Document Interface (MDI) und das Zusammenführen von Menüs, QuickInfos und Überlauf. Sie können die Verwendbarkeit und Lesbarkeit des Menüs durch Hinzufügen von Zugriffstasten, Tastenkombinationen, Häkchen, Bildern und Trennlinien verbessern.  
  
 Die <xref:System.Windows.Forms.MenuStrip> -Steuerelement ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.MainMenu> steuern; allerdings die <xref:System.Windows.Forms.MainMenu> Steuerelement wird für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, falls gewünscht.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Verwendungsmöglichkeiten für das MenuStrip-Steuerelement  
 Verwenden der <xref:System.Windows.Forms.MenuStrip> zu steuern:  
  
-   Erstellen Sie leicht anpassbare, häufig verwendete Menüs, die unterstützen erweiterte Benutzer Schnittstelle und das Layout-Funktionen, z. B. Text und Bild Sortierung und Ausrichtung, Drag & Drop-Vorgänge MDI, Überlauf und alternative Modi für den Zugriff auf Befehle im Menü.  
  
-   Das typische Aussehen und Verhalten des Betriebssystems zu unterstützen.  
  
-   Behandeln Sie Ereignisse einheitlich für alle Container und enthaltene Elemente, auf die gleiche Weise behandeln von Ereignissen für andere Steuerelemente.  
  
 Die folgende Tabelle zeigt einige besonders wichtigen Eigenschaften der <xref:System.Windows.Forms.MenuStrip> und die zugehörigen Klassen.  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ruft ab oder legt die <xref:System.Windows.Forms.ToolStripMenuItem> , wird verwendet, um eine Liste von untergeordneten MDI-Formularen anzuzeigen.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ruft ab oder legt sie fest, wie untergeordnete Menüs mit übergeordneten Menüs im MDI-Anwendungen zusammengeführt werden.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Ruft ab oder legt die Position eines zusammengeführten Elements in einem Menü im MDI-Anwendungen fest.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ruft ab oder legt einen Wert, der angibt, ob das Formular ein Container für untergeordnete MDI-Formulare ist.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ruft ab oder legt einen Wert, der angibt, ob QuickInfos, für angezeigt werden die <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.MenuStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ruft ab oder legt ihn fest zugeordneten Tastenkombinationen der <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ruft ab oder legt ein Wert, der angibt, ob die Tastenkombination zugeordnet sind die <xref:System.Windows.Forms.ToolStripMenuItem> abfragedarstellung neben der <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 Die folgende Tabelle zeigt die wichtigen <xref:System.Windows.Forms.MenuStrip> Assistentenklassen.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Stellt eine auswählbare Option angezeigt, die auf eine <xref:System.Windows.Forms.MenuStrip> oder <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Stellt ein Kontextmenü dar.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Stellt ein Steuerelement, können ein einzelnes Element aus einer Liste auszuwählen, die angezeigt wird, wenn der Benutzer klickt auf, eine <xref:System.Windows.Forms.ToolStripDropDownButton> oder ein Menüelement.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Stellt grundlegende Funktionen für Steuerelemente abgeleitet <xref:System.Windows.Forms.ToolStripItem> , Dropdownelementen beim anzeigen.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
