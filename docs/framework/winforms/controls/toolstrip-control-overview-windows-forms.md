---
title: "&#220;bersicht &#252;ber das ToolStrip-Steuerelement (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Toolstrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Symbolleisten [Windows Forms]"
  - "Symbolleisten [Windows Forms], Neuigkeiten in Windows Forms"
  - "ToolStrip-Steuerelement [Windows Forms], Informationen über das ToolStrip-Steuerelement"
  - "Neuigkeiten [Windows Forms], Symbolleisten"
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# &#220;bersicht &#252;ber das ToolStrip-Steuerelement (Windows Forms)
Das Windows Forms\-<xref:System.Windows.Forms.ToolStrip>\-Steuerelement und die zugehörigen Klassen stellen ein allgemeines Framework zum Zusammenfassen von Benutzeroberflächenelementen in Symbolleisten, Statusleisten und Menüs bereit.  <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente bieten eine umfangreiche Entwurfszeiterfahrung, zu der die direkte Aktivierung und Bearbeitung, benutzerdefinierte Layouts und Rafting, d. h. die gemeinsame Verwendung von horizontalen und vertikalen Bereichen durch Symbolleisten, zählen.  
  
 Obwohl <xref:System.Windows.Forms.ToolStrip> im Vergleich zu früheren Versionen Funktionen ersetzt und erweitert, wird die <xref:System.Windows.Forms.ToolBar> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
## Features von ToolStrip\-Steuerelementen  
 Verwenden Sie das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement wie folgt:  
  
-   Präsentieren Sie eine containerübergreifende, allgemeine Benutzeroberfläche.  
  
-   Erstellen Sie leicht anpassbare, häufig verwendete Symbolleisten, die erweiterte Benutzeroberflächen\- und Layoutfeatures unterstützen, z. B. Andocken, Rafting, Schaltflächen mit Text und Bildern, Dropdownschaltflächen und \-steuerelemente, Überlaufschaltflächen und Neuanordnung von <xref:System.Windows.Forms.ToolStrip>\-Elementen zur Laufzeit.  
  
-   Unterstützen Sie Überlauf und Neuanordnung von Elementen zur Laufzeit.  Das Überlauffeature verschiebt Elemente in ein Dropdownmenü, wenn sie aus Platzgründen nicht in einem <xref:System.Windows.Forms.ToolStrip> angezeigt werden können.  
  
-   Unterstützen Sie die typische Darstellung und das Verhalten des Betriebssystems durch ein allgemeines Darstellungsmodell.  
  
-   Behandeln Sie Ereignisse für alle Container und darin enthaltenen Elemente immer gleich, d. h. ebenso wie Ereignisse für andere Steuerelemente.  
  
-   Ziehen Sie Elemente von einem <xref:System.Windows.Forms.ToolStrip> in ein anderes bzw. innerhalb eines <xref:System.Windows.Forms.ToolStrip>.  
  
-   Erstellen Sie Dropdownsteuerelemente und Benutzeroberflächen\-Typ\-Editoren mit erweiterten Layouts in einem <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Verwenden Sie die <xref:System.Windows.Forms.ToolStripControlHost>\-Klasse, um andere Steuerelemente auf einem <xref:System.Windows.Forms.ToolStrip> zu verwenden und <xref:System.Windows.Forms.ToolStrip>\-Funktionen für sie zu erhalten.  
  
 Sie können die Funktionen ergänzen und das Aussehen und Verhalten ändern, indem Sie die Steuerelemente <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer> und <xref:System.Windows.Forms.ToolStripManager> zusammen mit der <xref:System.Windows.Forms.ToolStripRenderMode>\-Enumeration und <xref:System.Windows.Forms.ToolStripManagerRenderMode>\-Enumeration verwenden.  
  
 Das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement ist in hohem Maße konfigurierbar und erweiterbar und stellt zahlreiche Eigenschaften, Methoden und Ereignisse bereit, um das Aussehen und Verhalten anzupassen.  Im Folgenden werden einige wichtige Member aufgeführt:  
  
### Wichtige ToolStrip\-Member  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ruft ab bzw. legt fest, an welchen Rand des übergeordneten Containers ein <xref:System.Windows.Forms.ToolStrip> angedockt ist.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, ob Drag & Drop und die Neuanordnung von Elementen von der <xref:System.Windows.Forms.ToolStrip>\-Klasse privat behandelt werden.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ruft einen Wert ab bzw. legt einen Wert fest, der angibt, wie <xref:System.Windows.Forms.ToolStrip> das Layout seiner Elemente handhabt.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ruft ab bzw. legt fest, ob ein <xref:System.Windows.Forms.ToolStripItem> an das <xref:System.Windows.Forms.ToolStrip> oder den <xref:System.Windows.Forms.ToolStripOverflowButton> angefügt ist oder sich unverankert zwischen diesen befindet.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ruft einen Wert ab, der angibt, ob ein <xref:System.Windows.Forms.ToolStripItem> andere Elemente in einer Dropdownliste anzeigt, wenn Sie auf das <xref:System.Windows.Forms.ToolStripItem> klicken.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ruft das <xref:System.Windows.Forms.ToolStripItem> ab, das der Überlaufschaltfläche für ein <xref:System.Windows.Forms.ToolStrip> mit aktiviertem Überlauf entspricht.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ruft ein <xref:System.Windows.Forms.ToolStripRenderer> ab bzw. legt dieses fest, um das Aussehen und Verhalten eines <xref:System.Windows.Forms.ToolStrip> anzupassen.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ruft die Zeichenstile ab bzw. legt diese fest, die auf <xref:System.Windows.Forms.ToolStrip> angewendet werden sollen.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Wird ausgelöst, wenn sich die <xref:System.Windows.Forms.ToolStrip.Renderer%2A>\-Eigenschaft ändert.|  
  
 Die Flexibilität des <xref:System.Windows.Forms.ToolStrip>\-Steuerelements wird durch die Verwendung zahlreicher Assistentenklassen erreicht.  Nachfolgend werden einige der wichtigsten Assistentenklassen aufgeführt:  
  
### Wichtige ToolStrip\-Assistentenklassen  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.MenuStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.MainMenu>\-Klasse Funktionen hinzu.|  
|<xref:System.Windows.Forms.StatusStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.StatusBar>\-Klasse Funktionen hinzu.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Ersetzt und fügt der <xref:System.Windows.Forms.ContextMenu>\-Klasse Funktionen hinzu.|  
|<xref:System.Windows.Forms.ToolStripItem>|Abstrakte Basisklasse, die Ereignisse und Layouts für alle Elemente verwaltet, die ein <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost> oder <xref:System.Windows.Forms.ToolStripDropDown> enthalten kann.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Stellt einen Container mit einem Bereich auf jeder Seite des Formulars bereit, in dem Steuerelemente auf verschiedene Weise angeordnet werden können.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Behandelt die Zeichenfunktionen für <xref:System.Windows.Forms.ToolStrip>\-Objekte.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Stellt eine Darstellung im Stil von Microsoft Office bereit.|  
|<xref:System.Windows.Forms.ToolStripManager>|Steuert das Rendering und das Rafting von <xref:System.Windows.Forms.ToolStrip> sowie das Zusammenführen von Objekten vom Typ <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> und <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Legt den Zeichenstil \(benutzerdefiniert, Windows XP oder Microsoft Office Professional\) fest, der auf mehrere in einem Formular enthaltene <xref:System.Windows.Forms.ToolStrip>\-Objekte angewendet wird.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Legt den Zeichenstil \(benutzerdefiniert, Windows XP oder Microsoft Office Professional\) fest, der auf ein in einem Formular enthaltenem <xref:System.Windows.Forms.ToolStrip>\-Objekt angewendet wird.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hostet andere Steuerelemente, die keine spezifischen <xref:System.Windows.Forms.ToolStrip>\-Steuerelemente sind, die jedoch über <xref:System.Windows.Forms.ToolStrip>\-Funktionen verfügen sollen.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Legt fest, ob ein <xref:System.Windows.Forms.ToolStripItem> auf dem primären <xref:System.Windows.Forms.ToolStrip>, auf dem Überlauf\-<xref:System.Windows.Forms.ToolStrip> oder auf keinem angeordnet werden soll.|  
  
 Weitere Informationen finden Sie unter [Zusammenfassung der ToolStrip\-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) und [Architektur des ToolStrip\-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>