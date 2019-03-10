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
ms.openlocfilehash: c701ed6ff155ca507f827874a955b2361a3b2359
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719377"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Übersicht über das ToolStrip-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.ToolStrip> -Steuerelement und die zugehörigen Klassen bieten Sie ein gemeinsames Framework zum Zusammenfassen von Elementen der Benutzeroberfläche in Symbolleisten, Statusleisten und Menüs. <xref:System.Windows.Forms.ToolStrip> Steuerelemente bieten eine komfortable während der Entwurfszeit, die direkte Aktivierung und bearbeiten, benutzerdefiniertes Layout und rafting, enthält dies ist die Möglichkeit von Symbolleisten, horizontalen oder vertikalen Speicherplatz freizugeben.  
  
 Obwohl <xref:System.Windows.Forms.ToolStrip> ersetzt und funktionell erweitert, um das Steuerelement in früheren Versionen <xref:System.Windows.Forms.ToolBar> wird für Abwärtskompatibilität und zur künftigen Verwendung beibehalten, falls gewünscht.  
  
## <a name="features-of-the-toolstrip-controls"></a>Features von ToolStrip-Steuerelementen  
 Verwenden der <xref:System.Windows.Forms.ToolStrip> zu steuern:  
  
-   Stellen Sie eine gemeinsame Benutzeroberfläche in Containern.  
  
-   Erstellen Sie ganz einfach benutzerdefinierte, häufig angewandte Symbolleisten, die Unterstützung von erweiterten Features von Benutzer-Schnittstelle und das Layout, z. B. Schaltflächen, andocken, rafting mit Text und Bildern, Dropdown-Schaltflächen und Steuerelemente, überlaufen, Schaltflächen und Neuanordnen von der Laufzeit von <xref:System.Windows.Forms.ToolStrip> die Elemente.  
  
-   Überlauf und Neuanordnen von Elementen zur Laufzeit zu unterstützen. Die Überlauf-Funktion verschiebt Elemente in einem Dropdown-Menü, wenn nicht genügend Platz zum Anzeigen in einem <xref:System.Windows.Forms.ToolStrip>.  
  
-   Das typische Aussehen und Verhalten des Betriebssystems über ein gemeinsames Renderingmodell zu unterstützen.  
  
-   Behandeln von Ereignissen konsistent für alle Container und enthaltene Elemente, auf die gleiche Weise, die Sie behandeln Ereignisse für andere Steuerelemente.  
  
-   Ziehen Sie Elemente aus einer <xref:System.Windows.Forms.ToolStrip> in eine andere oder innerhalb einer <xref:System.Windows.Forms.ToolStrip>.  
  
-   Erstellen Sie die Benutzeroberflächen-Typ-Editoren Dropdown-Steuerelemente und einen Benutzer mit erweiterten Layouts in einer <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Verwenden Sie die <xref:System.Windows.Forms.ToolStripControlHost> -Klasse zur Verwendung von anderen Steuerelementen für eine <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.ToolStrip> Funktionen für sie.  
  
 Sie können die Funktionalität erweitern und ändern Sie das Aussehen und Verhalten mithilfe der <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, und <xref:System.Windows.Forms.ToolStripManager> zusammen mit den <xref:System.Windows.Forms.ToolStripRenderMode> und <xref:System.Windows.Forms.ToolStripManagerRenderMode> Enumerationen.  
  
 Die <xref:System.Windows.Forms.ToolStrip> Steuerelement ist hochgradig konfigurierbar und erweiterbar, und bietet viele Eigenschaften, Methoden und Ereignisse zum Anpassen von Aussehen und Verhalten. Im folgenden werden einige wichtige Member:  
  
### <a name="important-toolstrip-members"></a>Wichtige ToolStrip-Elemente  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ruft ab oder legt fest, welche Rand des übergeordneten Containers eine <xref:System.Windows.Forms.ToolStrip> angedockt ist.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob Drag &amp; Drop und die Neuanordnung von Elementen von der <xref:System.Windows.Forms.ToolStrip>-Klasse privat behandelt werden.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ruft ab oder legt einen Wert, der angibt, wie die <xref:System.Windows.Forms.ToolStrip> enthaltenen Elemente angeordnet.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ruft ab oder legt ihn fest, ob eine <xref:System.Windows.Forms.ToolStripItem> angefügt ist die <xref:System.Windows.Forms.ToolStrip> oder <xref:System.Windows.Forms.ToolStripOverflowButton> oder zwischen den beiden wechseln können.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ruft einen Wert, der angibt, ob eine <xref:System.Windows.Forms.ToolStripItem> andere Elemente in einer Dropdownliste anzeigt Liste, wenn die <xref:System.Windows.Forms.ToolStripItem> geklickt wird.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ruft das <xref:System.Windows.Forms.ToolStripItem>-Objekt ab, das der Überlaufschaltfläche für ein <xref:System.Windows.Forms.ToolStrip>-Objekt mit aktiviertem Überlauf entspricht.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ruft ab oder legt diesen fest eine <xref:System.Windows.Forms.ToolStripRenderer> zum Anpassen der Darstellung und Verhalten (Aussehen und Verhalten) verwendet eine <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Übernimmt oder bestimmt die Zeichenstile anzuwendende der <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Wird ausgelöst, wenn die <xref:System.Windows.Forms.ToolStrip.Renderer%2A> eigenschaftenänderungen.|  
  
 Die <xref:System.Windows.Forms.ToolStrip> des Steuerelements Flexibilität wird erreicht, durch die Verwendung von eine Reihe von begleitenden-Klassen. Im folgenden sind einige der wichtigsten:  
  
### <a name="important-toolstrip-companion-classes"></a>Wichtige ToolStrip Assistentenklassen  
  
|name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.MainMenu> Klasse.|  
|<xref:System.Windows.Forms.StatusStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.StatusBar> Klasse.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Ersetzt und funktionell erweitert, um die <xref:System.Windows.Forms.ContextMenu> Klasse.|  
|<xref:System.Windows.Forms.ToolStripItem>|Abstrakte Basisklasse, die Ereignisse und Layout für alle Elemente verwaltet, die eine <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, oder <xref:System.Windows.Forms.ToolStripDropDown> enthalten können.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Stellt einen Container mit einem Bereich auf jeder Seite des Formulars in der Steuerelemente auf verschiedene Weise angeordnet werden können.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Behandelt die Zeichenfunktionen für <xref:System.Windows.Forms.ToolStrip>-Objekte.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Stellt die Darstellung von Microsoft Office-Stil.|  
|<xref:System.Windows.Forms.ToolStripManager>|Steuert das Rendering und das Rafting von <xref:System.Windows.Forms.ToolStrip> sowie das Zusammenführen von Objekten vom Typ <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Gibt den Zeichnungsstil (Benutzerdefiniert, Windows XP oder Microsoft Office Professional), die mit mehreren <xref:System.Windows.Forms.ToolStrip> in einem Formular enthaltenen Objekte.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Gibt den Zeichnungsstil (Benutzerdefiniert, Windows XP oder Microsoft Office Professional), die auf einen <xref:System.Windows.Forms.ToolStrip> Objekt in einem Formular enthalten ist.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Andere Steuerelemente, die nicht speziell hostet <xref:System.Windows.Forms.ToolStrip> Steuerelemente jedoch für die Sie möchten <xref:System.Windows.Forms.ToolStrip> Funktionalität.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Gibt an, ob eine <xref:System.Windows.Forms.ToolStripItem> besteht darin, auf dem hauptblatt angeordnet werden <xref:System.Windows.Forms.ToolStrip>, auf dem Überlauf- <xref:System.Windows.Forms.ToolStrip>, oder keines von beiden.|  
  
 Weitere Informationen finden Sie unter [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md) und [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
