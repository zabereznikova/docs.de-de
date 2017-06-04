---
title: "&#220;bersicht &#252;ber die HelpProvider-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "HelpProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Dialogfelder, Kontextbezogene Hilfe"
  - "F1-Hilfe, Hinzufügen zu Windows Forms"
  - "Hilfe, Hinzufügen zu Windows-Anwendungen"
  - "HelpProvider-Komponente [Windows Forms], Informationen über die HelpProvider-Komponente"
  - "Windows Forms, Kontextbezogene Hilfe"
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# &#220;bersicht &#252;ber die HelpProvider-Komponente (Windows&#160;Forms)
Die [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)\-Komponente von Windows Forms wird verwendet, um eine HTML Help 1.x\-Hilfedatei \(entweder eine mit HTML Help Workshop erstellte CHM\-Datei oder eine HTM\-Datei\) mit einer Windows\-Anwendung zu verknüpfen.  Sie können auf mehrere Arten Hilfe zur Verfügung stellen:  
  
-   Bereitstellen von kontextabhängiger Hilfe für Steuerelemente auf Windows Forms  
  
-   Bereitstellen von kontextabhängiger Hilfe zu einem bestimmten Dialogfeld oder zu bestimmten Steuerelementen in einem Dialogfeld  
  
-   Öffnen einer Hilfedatei zu bestimmten Bereichen, z. B. die Hauptseite des Inhaltsverzeichnisses, Index oder eine Suchfunktion  
  
## Verwenden der HelpProvider\-Komponente  
 Durch Hinzufügen einer <xref:System.Windows.Forms.HelpProvider>\-Komponente zu einem Windows Form können die anderen Steuerelemente auf dem Formular die Help\-Eigenschaften der <xref:System.Windows.Forms.HelpProvider>\-Komponente verfügbar machen.  Dadurch können Sie Hilfe für die Steuerelemente auf dem Windows Form bereitstellen.  Sie können der <xref:System.Windows.Forms.HelpProvider>\-Komponente mit der <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>\-Eigenschaft eine Hilfedatei zuordnen.  Sie können den Typ der bereitgestellten Hilfe angeben, indem Sie <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> aufrufen und einen Wert aus der <xref:System.Windows.Forms.HelpNavigator>\-Enumeration für das angegebene Steuerelement bereitstellen.  Das Schlüsselwort oder Thema für die Hilfe wird durch Aufrufen der <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>\-Methode bereitgestellt.  
  
 Sie können eine bestimmte Hilfezeichenfolge mit der <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>\-Methode auch einem anderen Steuerelement zuordnen.  Die Zeichenfolge, die Sie über diese Methode mit einem Steuerelement verknüpfen, wird in einem Popupfenster angezeigt, wenn der Benutzer die Taste F1 drückt, während der Fokus auf dem Steuerelement liegt.  
  
 Wenn <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> nicht festgelegt wurde, müssen Sie den Hilfetext mit <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> bereitstellen.  Wenn Sie sowohl <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> als auch die Hilfezeichenfolge festgelegt haben, hat die Hilfe auf der Basis von <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Vorrang.  
  
> [!NOTE]
>  Wenn Sie den Pfad zur Hilfedatei in der <xref:System.Windows.Forms.Help.ShowHelp%2A>\-Methode oder der <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>\-Eigenschaft des <xref:System.Windows.Forms.HelpProvider>\-Steuerelements angeben, können bei Verwendung des relativen Pfads Probleme auftreten.  Daher sollten Sie zur Angabe der Hilfedatei unbedingt den absoluten Dateipfad verwenden.  
  
## Siehe auch  
 [Hilfesysteme in Windows Forms\-Anwendungen](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)