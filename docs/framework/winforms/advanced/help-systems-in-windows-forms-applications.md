---
title: "Hilfesysteme in Windows Forms-Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Hilfe, Hinzufügen zu Windows-Anwendungen"
  - "Hilfe, Windows Forms"
  - "HelpProvider-Komponente [Windows Forms], Bereitstellen von Hilfe in Windows-Anwendungen"
  - "Direkthilfe Hilfe"
  - "Windows-Anwendungen, Bereitstellen von Hilfesystemen"
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Hilfesysteme in Windows Forms-Anwendungen
Eine der wichtigsten Zusatzfunktionen, die Sie als Anwendungsentwickler den Benutzern zur Verfügung stellen können, ist ein angemessenes Hilfesystem.  Dieses wird von den Benutzern bei Zweifeln oder Unklarheiten konsultiert.  In einer Windows\-basierten Anwendung kann ein Hilfesystem problemlos mithilfe der [HelpProvider\-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) bereitgestellt werden.  
  
## Verschiedene Hilfetypen  
 Die <xref:System.Windows.Forms.HelpProvider>\-Komponente von Windows Forms wird verwendet, um eine HTML Help 1.x\-Hilfedatei \(entweder eine mit HTML Help Workshop erstellte CHM\-Datei oder eine HTM\-Datei\) mit einer Windows\-basierten Anwendung zu verknüpfen.  Die <xref:System.Windows.Forms.HelpProvider>\-Komponente kann verwendet werden, um kontextbezogene Hilfe für Steuerelemente in Windows Forms oder für bestimmte Steuerelemente zur Verfügung zu stellen.  Darüber hinaus kann durch die <xref:System.Windows.Forms.HelpProvider>\-Komponente eine Hilfedatei zu bestimmten Bereichen, z. B. die Hauptseite des Inhaltsverzeichnisses, ein Index oder eine Suchfunktion, aktiviert werden.  Allgemeine Informationen über die <xref:System.Windows.Forms.HelpProvider>\-Komponente finden Sie unter [Übersicht über die HelpProvider\-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).  Informationen über die Verwendung der <xref:System.Windows.Forms.HelpProvider>\-Komponente zum Anzeigen der Hilfe in Windows Forms finden Sie unter [Gewusst wie: Anzeigen der kontextbezogenen Hilfe](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  Informationen über die Verwendung der <xref:System.Windows.Forms.ToolTip>\-Komponente zum Anzeigen steuerelementspezifischer Hilfe finden Sie unter [Benutzerführung mithilfe von QuickInfos](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).  
  
 Mithilfe von HTML Help Workshop können Sie HTML Help 1.x\-Dateien generieren.  Weitere Informationen zur HTML\-Hilfe finden Sie unter "HTML Help Workshop" oder unter den anderen Themen zur HTML\-Hilfe in MSDN.  
  
## Siehe auch  
 [Integrieren von Benutzerhilfe in Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [HelpProvider\-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)   
 [ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)   
 [Übersicht über Windows Forms](../../../../docs/framework/winforms/windows-forms-overview.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)