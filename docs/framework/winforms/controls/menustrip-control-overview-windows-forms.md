---
title: "&#220;bersicht &#252;ber das MenuStrip-Steuerelement (Windows Forms) | Microsoft Docs"
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
  - "MenuStrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Menüs, Erstellen"
  - "MenuStrip-Steuerelement [Windows Forms], Informationen über das MenuStrip-Steuerelement"
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber das MenuStrip-Steuerelement (Windows Forms)
Menüs stellen Benutzern Funktionen in Form von Befehlen bereit, die nach einem gemeinsamen Design gruppiert sind.  
  
 Das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement ist in dieser Version von Visual Studio und .NET Framework neu.  Mit diesem Steuerelement können Sie problemlos Menüs wie in Microsoft Office erstellen.  
  
 Das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement unterstützt die MDI \(Multiple\-Document Interface\) sowie Menüzusammenführung, QuickInfos und Überlauf.  Sie können die Menüs benutzerfreundlicher gestalten, indem Sie Tastenkombinationen, Zugriffstasten, Häkchen, Bilder und Trennlinien hinzufügen.  
  
 Obwohl das <xref:System.Windows.Forms.MainMenu>\-Steuerelement durch das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement ersetzt und funktionell erweitert wird, wird das <xref:System.Windows.Forms.MainMenu>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
## Verwendungsmöglichkeiten des MenuStrip\-Steuerelements  
 Verwenden Sie das <xref:System.Windows.Forms.MenuStrip>\-Steuerelement wie folgt:  
  
-   Erstellen Sie leicht anpassbare, häufig verwendete Menüs, die anspruchsvolle Benutzeroberflächen\- und Layoutfeatures unterstützen, z. B. das Anordnen und Ausrichten von Text und Bildern, Drag & Drop\-Operationen, MDI, Überlauf und alternative Modi für den Zugriff auf Menübefehle.  
  
-   Unterstützen Sie das typische Aussehen und Verhalten des Betriebssystems.  
  
-   Behandeln Sie Ereignisse für alle Container und darin enthaltenen Elemente immer gleich, d. h. ebenso wie Ereignisse für andere Steuerelemente.  
  
 Die folgende Tabelle enthält einige besonders wichtige Eigenschaften von <xref:System.Windows.Forms.MenuStrip> und zugeordneten Klassen.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ruft das <xref:System.Windows.Forms.ToolStripMenuItem> ab, das verwendet wird, um eine Liste mit untergeordneten MDI\-Formularen anzuzeigen, bzw. legt dieses fest.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=fullName>|Ruft ab, wie untergeordnete Menüs in MDI\-Anwendungen mit übergeordneten Menüs zusammengeführt werden, bzw. legt dies fest.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=fullName>|Ruft die Position eines zusammengeführten Elements in einem Menü in MDI\-Anwendungen ab bzw. legt diese fest.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=fullName>|Ruft einen Wert ab, der angibt, ob das Formular ein Container für untergeordnete MDI\-Formulare ist, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ruft einen Wert ab, der angibt, ob QuickInfos für den <xref:System.Windows.Forms.MenuStrip> angezeigt werden, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ruft einen Wert ab, der angibt, ob der <xref:System.Windows.Forms.MenuStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ruft die Tastenkombinationen ab, die dem <xref:System.Windows.Forms.ToolStripMenuItem> zugeordnet sind, bzw. legt diese fest.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ruft einen Wert ab, der angibt, ob die Tastenkombinationen, die dem <xref:System.Windows.Forms.ToolStripMenuItem> zugeordnet sind, neben dem <xref:System.Windows.Forms.ToolStripMenuItem> angezeigt werden, bzw. legt diesen fest.|  
  
 In der folgenden Tabelle werden die wichtigen <xref:System.Windows.Forms.MenuStrip>\-Assistentenklassen angezeigt.  
  
|Klasse|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Stellt eine Option dar, die in einem <xref:System.Windows.Forms.MenuStrip> oder einem <xref:System.Windows.Forms.ContextMenuStrip> angezeigt wird, und die ausgewählt werden kann.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Stellt ein Kontextmenü dar.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Stellt ein Kontextmenü dar, das es dem Benutzer ermöglicht, ein einzelnes Element aus einer Liste auszuwählen, die angezeigt wird, wenn der Benutzer auf einen <xref:System.Windows.Forms.ToolStripDropDownButton> oder ein Menüelement auf einer höheren Ebene klickt.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Stellt grundlegende Funktionen für Steuerelemente bereit, die vom <xref:System.Windows.Forms.ToolStripItem> abgeleitet sind und Dropdownelemente anzeigen, wenn darauf geklickt wird.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>