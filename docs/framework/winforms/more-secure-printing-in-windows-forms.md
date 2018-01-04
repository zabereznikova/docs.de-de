---
title: "Mehr Sicherheit beim Drucken in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f36ee150e4dcca74141b644a55451abd4a4fd21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="more-secure-printing-in-windows-forms"></a>Mehr Sicherheit beim Drucken in Windows Forms
Windows Forms-Anwendungen enthalten häufig drucken Fähigkeiten. Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verwendet die <xref:System.Drawing.Printing.PrintingPermission> Klasse zum Steuern des Zugriffs auf Druckfunktionen und den zugehörigen <xref:System.Drawing.Printing.PrintingPermissionLevel> Enumerationswert, auf die Ebene des Zugriffs anzugeben. Drucken ist standardmäßig in den Zonen Lokales Intranet und Internet aktiviert; Allerdings ist die Ebene des Zugriffs in beiden Zonen eingeschränkt. Ob Ihre Anwendung drucken kann, muss der Benutzer eingreifen, oder kann nicht drucken hängt von den Wert für die Berechtigung für die Anwendung gewährt. Standardmäßig erhält die lokalen Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> Zugriff und der Intranetzone empfängt <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> Zugriff.  
  
 Die folgende Tabelle zeigt die verfügbaren Funktionen auf jeder Berechtigungsebene der drucken.  
  
|PrintingPermissionLevel|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Bietet vollständigen Zugriff auf alle installierten Drucker.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Ermöglicht programmgesteuerten Drucken auf dem Standarddrucker und sicheres Drucken über ein eingeschränktes Dialogfeld. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Ermöglicht das Drucken nur über ein eingeschränktes Dialogfeld. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Verhindert den Zugriff auf Drucker. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Siehe auch  
 [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Weitere Überlegungen zur Sicherheit in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)
