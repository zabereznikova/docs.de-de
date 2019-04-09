---
title: Mehr Sicherheit beim Drucken in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 5ee170980ed02d90606c774e2a7055f047292e33
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197359"
---
# <a name="more-secure-printing-in-windows-forms"></a>Mehr Sicherheit beim Drucken in Windows Forms
Windows Forms-Anwendungen umfassen häufig drucken Fähigkeiten. Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verwendet die <xref:System.Drawing.Printing.PrintingPermission> Klasse zum Steuern des Zugriffs auf Funktionen zum Drucken und den zugehörigen <xref:System.Drawing.Printing.PrintingPermissionLevel> Enumerationswert, der die Ebene des Zugriffs angibt. Drucken ist standardmäßig in der lokalen Intranetzone und Zonen standardmäßig aktiviert; die Zugriffsebene ist jedoch in beiden Zonen beschränkt. Ob Ihre Anwendung gedruckt werden kann, muss der Benutzer eingreifen, oder kann nicht drucken hängt von der Berechtigungswert, der für die Anwendung gewährt. Standardmäßig erhält die lokale Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> Zugriff und der Intranetzone empfängt <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> Zugriff.  
  
 Die folgende Tabelle zeigt die verfügbaren Funktionen auf jeder Berechtigungsebene der Druck.  
  
|PrintingPermissionLevel|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Bietet vollständigen Zugriff auf alle installierten Drucker.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Ermöglicht den programmgesteuerten drucken den Standarddrucker und sicheres Drucken über ein eingeschränktes Dialogfeld. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> ist eine Teilmenge der <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Ermöglicht das Drucken ausschließlich über ein eingeschränktes Dialogfeld. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ist eine Teilmenge der <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Verhindert den Zugriff auf Drucker. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> ist eine Teilmenge der <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Siehe auch

- [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Weitere Überlegungen zur Sicherheit in Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Übersicht über die Sicherheit in Windows Forms](security-in-windows-forms-overview.md)
- [Sicherheit in Windows Forms](windows-forms-security.md)
