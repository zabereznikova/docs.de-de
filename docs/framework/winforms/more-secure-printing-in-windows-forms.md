---
title: "Mehr Sicherheit beim Drucken in Windows&#160;Forms | Microsoft Docs"
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
  - "Drucken [Windows Forms], Sicherheit"
  - "PrintingPermission-Klasse, Windows Forms-Sicherheit"
  - "Sicherheit [Windows Forms], Drucken"
  - "Windows Forms, Drucken"
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Mehr Sicherheit beim Drucken in Windows&#160;Forms
In Windows Forms\-Anwendungen stehen oftmals Druckfunktionen zur Verfügung.  In [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] wird der Zugriff auf Druckfunktionen und dem zugehörigen <xref:System.Drawing.Printing.PrintingPermissionLevel>\-Enumerationswert zum Angeben der Zugriffsebene mit der <xref:System.Drawing.Printing.PrintingPermission>\-Klasse gesteuert.  In der Standardeinstellung sind die Druckfunktionen in der lokalen Intranetzone und der Internetzone aktiviert. In beiden Zonen ist die Zugriffsebene jedoch eingeschränkt.  Ob in einer Anwendung das Drucken möglich, nicht möglich oder die Interaktion mit dem Benutzer erforderlich ist, hängt von der ihr zugewiesenen Zugriffsberechtigung ab.  In der Standardeinstellung erhält die lokale Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel>\-Zugriff, während die Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel>\-Zugriff erhält.  
  
 In der folgenden Tabelle sind die Funktionen aufgeführt, die auf den jeweiligen Druckberechtigungsebenen verfügbar sind.  
  
|PrintingPermissionLevel|Beschreibung|  
|-----------------------------|------------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Bietet uneingeschränkten Zugriff auf alle installierten Drucker.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Aktiviert programmgesteuertes Drucken auf dem Standarddrucker und sicheres Drucken über ein eingeschränktes Dialogfeld.  <xref:System.Drawing.Printing.PrintingPermissionLevel> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Ermöglicht das Drucken ausschließlich über ein eingeschränkteres Dialogfeld.  <xref:System.Drawing.Printing.PrintingPermissionLevel> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel>|Verhindert den Zugriff auf Drucker.  <xref:System.Drawing.Printing.PrintingPermissionLevel> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel>.|  
  
## Siehe auch  
 [Mehr Sicherheit beim Datei\- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Weitere Überlegungen zur Sicherheit in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)   
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)