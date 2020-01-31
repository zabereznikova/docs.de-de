---
title: Übersicht über das ToolStrip-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741077"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Übersicht über das ToolStrip-Steuerelement (Windows Forms)
Die Windows Forms <xref:System.Windows.Forms.ToolStrip>-Steuerelement und die zugehörigen Klassen bieten ein gängiges Framework zum Kombinieren von Benutzeroberflächen Elementen in Symbolleisten, Status leisten und Menüs. <xref:System.Windows.Forms.ToolStrip> Steuerelemente bieten eine umfangreiche Entwurfszeit-Benutzerfreundlichkeit, die eine direkte Aktivierung und Bearbeitung, ein benutzerdefiniertes Layout und ein Rafting umfasst. Dies ist die Fähigkeit von Symbolleisten, horizontalen oder vertikalen Raum freizugeben.  
  
 Obwohl <xref:System.Windows.Forms.ToolStrip> in früheren Versionen ersetzt und dem Steuerelement Funktionen hinzufügt, wird <xref:System.Windows.Forms.ToolBar> bei Bedarf sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten.  
  
## <a name="features-of-the-toolstrip-controls"></a>Funktionen der ToolStrip-Steuerelemente  
 Verwenden Sie das <xref:System.Windows.Forms.ToolStrip>-Steuerelement für Folgendes:  
  
- Stellen Sie eine gemeinsame Benutzeroberfläche in Containern dar.  
  
- Erstellen Sie einfach angepasste, häufig verwendete Symbolleisten, die erweiterte Benutzeroberflächen-und Layoutfeatures unterstützen, wie z. b. andocken, Rafting, Schaltflächen mit Text und Bildern, Dropdown-Schaltflächen und-Steuerelemente, Überlauf Schaltflächen und Lauf Zeit Neuanordnung von <xref:System.Windows.Forms.ToolStrip> Elementen  
  
- Unterstützung von Überlauf-und Lauf Zeitelement-Neuanordnung von Elementen. Die Überlauf Funktion verschiebt Elemente in ein Dropdown Menü, wenn nicht genügend Platz vorhanden ist, um Sie in einem <xref:System.Windows.Forms.ToolStrip>anzuzeigen.  
  
- Unterstützen Sie das typische Aussehen und Verhalten des Betriebssystems durch ein gängiges Renderingmodell.  
  
- Behandeln Sie Ereignisse konsistent für alle Container und enthaltenen Elemente auf die gleiche Weise wie Ereignisse für andere Steuerelemente.  
  
- Ziehen Sie Elemente von einem <xref:System.Windows.Forms.ToolStrip> zu einem anderen oder innerhalb eines <xref:System.Windows.Forms.ToolStrip>.  
  
- Erstellen Sie Dropdown-Steuerelemente und benutzerschnittstellentyp-Editoren mit erweiterten Layouts in einer <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Verwenden Sie die <xref:System.Windows.Forms.ToolStripControlHost>-Klasse, um andere Steuerelemente auf einem <xref:System.Windows.Forms.ToolStrip> zu verwenden, und erhalten Sie <xref:System.Windows.Forms.ToolStrip> Funktionalität für Sie.  
  
 Sie können die Funktionalität erweitern und die Darstellung und das Verhalten ändern, indem Sie die <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>und <xref:System.Windows.Forms.ToolStripManager> zusammen mit den <xref:System.Windows.Forms.ToolStripRenderMode>-und <xref:System.Windows.Forms.ToolStripManagerRenderMode>-Enumerationen verwenden.  
  
 Das <xref:System.Windows.Forms.ToolStrip> Steuerelement ist hochgradig konfigurier Bar und erweiterbar und bietet viele Eigenschaften, Methoden und Ereignisse, um Darstellung und Verhalten anzupassen. Unten sind einige wichtige Mitglieder aufgeführt:  
  
### <a name="important-toolstrip-members"></a>Wichtige ToolStrip-Member  
  
|-Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ruft den Rand des übergeordneten Containers ab, an den ein <xref:System.Windows.Forms.ToolStrip> angedockt ist, oder legt diesen fest.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob Drag &amp; Drop und die Neuanordnung von Elementen von der <xref:System.Windows.Forms.ToolStrip>-Klasse privat behandelt werden.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ruft einen Wert ab, der angibt, wie die <xref:System.Windows.Forms.ToolStrip> seine Elemente festlegt, oder legt diesen fest.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ruft ab oder legt fest, ob ein <xref:System.Windows.Forms.ToolStripItem> an die <xref:System.Windows.Forms.ToolStrip> oder <xref:System.Windows.Forms.ToolStripOverflowButton> angefügt ist oder zwischen den beiden hängen kann.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ruft einen Wert ab, der angibt, ob ein <xref:System.Windows.Forms.ToolStripItem> andere Elemente in einer Dropdown Liste anzeigt, wenn auf die <xref:System.Windows.Forms.ToolStripItem> geklickt wird.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ruft das <xref:System.Windows.Forms.ToolStripItem>-Objekt ab, das der Überlaufschaltfläche für ein <xref:System.Windows.Forms.ToolStrip>-Objekt mit aktiviertem Überlauf entspricht.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ruft einen <xref:System.Windows.Forms.ToolStripRenderer> ab oder legt ihn fest, der zum Anpassen der Darstellung und des Verhaltens (Aussehen und Verhalten) eines <xref:System.Windows.Forms.ToolStrip>verwendet wird.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ruft die Zeichnungs Stile ab, die auf die <xref:System.Windows.Forms.ToolStrip>angewendet werden sollen, oder legt diese fest.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Wird ausgelöst, wenn sich die <xref:System.Windows.Forms.ToolStrip.Renderer%2A>-Eigenschaft ändert.|  
  
 Die Flexibilität des <xref:System.Windows.Forms.ToolStrip> Steuer Elements wird durch die Verwendung einer Reihe von begleitenden Klassen erreicht. Unten sind einige der bemerkenswertesten:  
  
### <a name="important-toolstrip-companion-classes"></a>Wichtige ToolStrip-Begleit Klassen  
  
|-Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.MainMenu>-Klasse Funktionalität hinzu.|  
|<xref:System.Windows.Forms.StatusStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.StatusBar>-Klasse Funktionalität hinzu.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.ContextMenu>-Klasse Funktionalität hinzu.|  
|<xref:System.Windows.Forms.ToolStripItem>|Abstrakte Basisklasse, die Ereignisse und Layout für alle Elemente verwaltet, die ein <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>oder <xref:System.Windows.Forms.ToolStripDropDown> enthalten kann.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Stellt einen Container mit einem Panel auf jeder Seite des Formulars bereit, in dem Steuerelemente auf verschiedene Arten angeordnet werden können.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Behandelt die Zeichenfunktionen für <xref:System.Windows.Forms.ToolStrip>-Objekte.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Stellt Microsoft Office Darstellung bereit.|  
|<xref:System.Windows.Forms.ToolStripManager>|Steuert das Rendering und das Rafting von <xref:System.Windows.Forms.ToolStrip> sowie das Zusammenführen von Objekten vom Typ <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Gibt den Zeichnungs Stil (Custom, Windows XP oder Microsoft Office Professional) an, der auf mehrere in einem Formular enthaltene <xref:System.Windows.Forms.ToolStrip> Objekte angewendet wird.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Gibt den Zeichnungs Stil (Custom, Windows XP oder Microsoft Office Professional) an, der auf ein in einem Formular enthaltenes <xref:System.Windows.Forms.ToolStrip> Objekt angewendet wird.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hostet andere Steuerelemente, bei denen es sich nicht um <xref:System.Windows.Forms.ToolStrip> Steuerelemente handelt, für die Sie <xref:System.Windows.Forms.ToolStrip> Funktionalität benötigen.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Gibt an, ob ein <xref:System.Windows.Forms.ToolStripItem> auf der Haupt <xref:System.Windows.Forms.ToolStrip>, auf der Überlauf <xref:System.Windows.Forms.ToolStrip>oder auf keinem der beiden festgelegt werden soll.|  
  
 Weitere Informationen finden Sie unter [ToolStrip-Technologie Zusammenfassung](toolstrip-technology-summary.md) und [ToolStrip-Steuerelement Architektur](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
