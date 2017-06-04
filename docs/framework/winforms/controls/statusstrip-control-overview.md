---
title: "&#220;bersicht &#252;ber das StatusStrip-Steuerelement | Microsoft Docs"
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
  - "StatusStrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Statusleisten, Informationen über Statusleisten"
  - "StatusStrip-Steuerelement [Windows Forms], Informationen über das StatusStrip-Steuerelement"
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# &#220;bersicht &#252;ber das StatusStrip-Steuerelement
Ein <xref:System.Windows.Forms.StatusStrip>\-Steuerelement zeigt Informationen zu einem Objekt an, das in einem <xref:System.Windows.Forms.Form> angezeigt wird, zu den Komponenten des Objekts oder Kontextinformationen, die sich auf die Operation dieses Objekts in Ihrer Anwendung beziehen.  Ein <xref:System.Windows.Forms.StatusStrip>\-Steuerelement besteht normalerweise aus <xref:System.Windows.Forms.ToolStripStatusLabel>\-Objekten, von denen jedes Text, ein Symbol oder beides anzeigt.  Der <xref:System.Windows.Forms.StatusStrip> kann zudem auch <xref:System.Windows.Forms.ToolStripDropDownButton>\-, <xref:System.Windows.Forms.ToolStripSplitButton> und <xref:System.Windows.Forms.ToolStripProgressBar>\-Steuerelemente enthalten.  
  
 Der standardmäßige <xref:System.Windows.Forms.StatusStrip> weist keine Panels auf.  Verwenden Sie die <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=fullName>\-Methode, um einem <xref:System.Windows.Forms.StatusStrip> Panels hinzuzufügen.  
  
 Es gibt umfassende Unterstützung für den Umgang mit <xref:System.Windows.Forms.StatusStrip>\-Elementen und häufig verwendeten Befehle in Visual Studio.  
  
 Siehe auch [Dialogfeld "StatusStrip\-Aufgaben"](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)) unter [StatusStrip\-Elementauflistungs\-Editor](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)).  
  
 Obwohl <xref:System.Windows.Forms.StatusStrip> das <xref:System.Windows.Forms.StatusBar>\-Steuerelement vorheriger Versionen ersetzt und erweitert, wird das <xref:System.Windows.Forms.StatusBar>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
### Wichtige StatusStrip\-Member  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|Ruft einen Wert ab, der angibt, ob <xref:System.Windows.Forms.StatusStrip> Überlauffunktionen unterstützt, bzw. legt diesen fest.|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|Ruft einen Wert ab, der angibt, ob sich das <xref:System.Windows.Forms.StatusStrip>\-Objekt in seinem <xref:System.Windows.Forms.ToolStripContainer>\-Objekt von einem Ende zum anderen Ende erstreckt, oder legt diesen Wert fest.|  
  
### Wichtige StatusStrip\-Begleitklassen  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Stellt ein Panel in einem <xref:System.Windows.Forms.StatusStrip>\-Steuerelement dar.|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Zeigt eine zugehörige <xref:System.Windows.Forms.ToolStripDropDown> an, aus der der Benutzer ein einzelnes Element auswählen kann.|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Stellt ein zweiteiliges Steuerelement dar, das aus einer Standardschaltfläche und einem Dropdownmenü besteht.|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Zeigt den Fortschrittsstatus eines Prozesses an.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>