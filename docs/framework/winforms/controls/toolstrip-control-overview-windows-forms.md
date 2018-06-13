---
title: Übersicht über das ToolStrip-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 3927f180e738541f2f2f8af6d03d281f6a601167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542050"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Übersicht über das ToolStrip-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolStrip> -Steuerelement und die zugehörigen Klassen bieten ein allgemeines Framework zum Zusammenfassen von Benutzeroberflächenelementen in Symbolleisten, Statusleisten und Menüs. <xref:System.Windows.Forms.ToolStrip> Steuerelemente bieten eine komfortable während der Entwurfszeit, die direkte Aktivierung und bearbeiten, benutzerdefiniertes Layout und rafting, umfasst also die Möglichkeit von Symbolleisten, horizontalen oder vertikalen Abstand gemeinsam verwenden.  
  
 Obwohl <xref:System.Windows.Forms.ToolStrip> ersetzt und funktionell erweitert, um das Steuerelement in früheren Versionen <xref:System.Windows.Forms.ToolBar> wird für Abwärtskompatibilität und für zukünftige Verwendung beibehalten, falls gewünscht.  
  
## <a name="features-of-the-toolstrip-controls"></a>Features von ToolStrip-Steuerelementen  
 Verwenden der <xref:System.Windows.Forms.ToolStrip> zu steuern:  
  
-   Stellen Sie eine gemeinsame Benutzeroberfläche in Containern.  
  
-   Erstellen Sie leicht anpassbare, häufig verwendete Symbolleisten, die unterstützt erweiterte Benutzer Schnittstelle und das Layout-Funktionen, wie z. B. andocken, rafting, Schaltflächen mit Text und Bildern, Dropdown-Schaltflächen und Steuerelemente, "Überlauf", Schaltflächen und zur Laufzeit neu zu ordnen <xref:System.Windows.Forms.ToolStrip> Elemente.  
  
-   Überlauf und die Neuordnung von zur Laufzeit zu unterstützen. Verschiebt die Überlauf-Funktion Elemente zu einem Dropdown-Menü, wenn nicht ausreichend Platz zur Anzeige in einem <xref:System.Windows.Forms.ToolStrip>.  
  
-   Das typische Aussehen und Verhalten des Betriebssystems über ein gemeinsames Renderingmodell zu unterstützen.  
  
-   Behandeln Sie Ereignisse einheitlich für alle Container und enthaltene Elemente, auf die gleiche Weise behandeln von Ereignissen für andere Steuerelemente.  
  
-   Ziehen Sie Elemente aus einer <xref:System.Windows.Forms.ToolStrip> in eine andere oder innerhalb einer <xref:System.Windows.Forms.ToolStrip>.  
  
-   Erstellen Sie die Benutzeroberflächen-Typ-Editoren Dropdownsteuerelemente und Benutzer mit erweiterten Layouts in einem <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Verwenden der <xref:System.Windows.Forms.ToolStripControlHost> Klasse auf andere Steuerelemente verwenden eine <xref:System.Windows.Forms.ToolStrip> Webs <xref:System.Windows.Forms.ToolStrip> Funktionen für sie.  
  
 Sie können die Funktionalität erweitern, und ändern Sie das Aussehen und Verhalten mithilfe der <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, und <xref:System.Windows.Forms.ToolStripManager> zusammen mit den <xref:System.Windows.Forms.ToolStripRenderMode> und <xref:System.Windows.Forms.ToolStripManagerRenderMode> Enumerationen.  
  
 Die <xref:System.Windows.Forms.ToolStrip> -Steuerelement ist hochgradig konfigurierbar und erweiterbar, und bietet viele Eigenschaften, Methoden und Ereignisse Aussehen und Verhalten anpassen. Im folgenden sind einige wichtige Member:  
  
### <a name="important-toolstrip-members"></a>Wichtige ToolStrip-Elemente  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ruft ab oder legt fest, welche Rand des übergeordneten Containers ein <xref:System.Windows.Forms.ToolStrip> angedockt ist.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob Drag & Drop und die Neuanordnung von Elementen von der <xref:System.Windows.Forms.ToolStrip>-Klasse privat behandelt werden.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ruft ab oder legt einen Wert, der angibt, wie die <xref:System.Windows.Forms.ToolStrip> enthaltenen Elemente angeordnet.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ruft ab oder legt sie fest, ob eine <xref:System.Windows.Forms.ToolStripItem> angefügt ist die <xref:System.Windows.Forms.ToolStrip> oder <xref:System.Windows.Forms.ToolStripOverflowButton> oder zwischen den beiden float können.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ruft einen Wert, der angibt, ob ein <xref:System.Windows.Forms.ToolStripItem> andere Elemente in einer Dropdownliste angezeigt Liste, wenn die <xref:System.Windows.Forms.ToolStripItem> geklickt wird.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ruft das <xref:System.Windows.Forms.ToolStripItem>-Objekt ab, das der Überlaufschaltfläche für ein <xref:System.Windows.Forms.ToolStrip>-Objekt mit aktiviertem Überlauf entspricht.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ruft ab oder legt ihn fest ein <xref:System.Windows.Forms.ToolStripRenderer> zum Anpassen der Darstellung und Verhalten (Aussehen und Verhalten) verwendet eine <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ruft ab oder legt die Standardzeichnungsstile anzuwendende der <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Wird ausgelöst, wenn die <xref:System.Windows.Forms.ToolStrip.Renderer%2A> -Eigenschaft ändert.|  
  
 Die <xref:System.Windows.Forms.ToolStrip> des Steuerelements Flexibilität wird durch die Verwendung einer Anzahl von Assistentenklassen erreicht. Im folgenden sind einige der besonders erwähnenswert:  
  
### <a name="important-toolstrip-companion-classes"></a>Wichtige ToolStrip-Assistentenklassen  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.MainMenu> Klasse.|  
|<xref:System.Windows.Forms.StatusStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.StatusBar> Klasse.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.ContextMenu> Klasse.|  
|<xref:System.Windows.Forms.ToolStripItem>|Abstrakte Basisklasse, die Ereignisse und Layout für alle Elemente verwaltet, die eine <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, oder <xref:System.Windows.Forms.ToolStripDropDown> enthalten können.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Stellt einen Container mit einem Bereich auf jeder Seite des Formulars in der Steuerelemente auf verschiedene Weise angeordnet werden können.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Behandelt die Zeichnungsfunktion für <xref:System.Windows.Forms.ToolStrip> Objekte.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Enthält die Darstellung von Microsoft Office-Stil.|  
|<xref:System.Windows.Forms.ToolStripManager>|Steuerelemente <xref:System.Windows.Forms.ToolStrip> Rendering und rafting und das Zusammenführen von <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, und <xref:System.Windows.Forms.ToolStripMenuItem> Objekte.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Gibt das Zeichnen-Format (Benutzerdefiniert, Windows XP oder Microsoft Office Professional) mit mehreren angewendet <xref:System.Windows.Forms.ToolStrip> in einem Formular enthaltenen Objekte.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Gibt das Zeichnen-Format (Benutzerdefiniert, Windows XP oder Microsoft Office Professional) angewendet werden, um eine <xref:System.Windows.Forms.ToolStrip> in einem Formular enthaltene Objekt.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Andere Steuerelemente, die nicht speziell sind hostet <xref:System.Windows.Forms.ToolStrip> Steuerelemente jedoch für den Sie möchten <xref:System.Windows.Forms.ToolStrip> Funktionalität.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Gibt an, ob eine <xref:System.Windows.Forms.ToolStripItem> wird auf der Hauptseite angeordnet werden, <xref:System.Windows.Forms.ToolStrip>, in der Überlaufspalte <xref:System.Windows.Forms.ToolStrip>, oder keines von beiden.|  
  
 Weitere Informationen finden Sie unter [Zusammenfassung der ToolStrip-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) und [Architektur des ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
