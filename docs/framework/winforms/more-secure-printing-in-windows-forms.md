---
title: Sicherere Druckfunktion
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734892"
---
# <a name="more-secure-printing-in-windows-forms"></a>Mehr Sicherheit beim Drucken in Windows Forms
Windows Forms Anwendungen enthalten häufig Druckfähigkeiten. Der .NET Framework verwendet die <xref:System.Drawing.Printing.PrintingPermission>-Klasse, um den Zugriff auf Druckfunktionen zu steuern, und den zugeordneten <xref:System.Drawing.Printing.PrintingPermissionLevel>-Enumerationswert, um die Zugriffsebene anzugeben. Standardmäßig ist das Drucken standardmäßig in den Zonen "Lokales Intranet" und "Internet" aktiviert. Allerdings ist die Zugriffsebene in beiden Zonen eingeschränkt. Ob die Anwendung gedruckt werden kann, eine Benutzerinteraktion erfordert oder nicht gedruckt werden kann, hängt vom Berechtigungs Wert ab, der der Anwendung gewährt wurde. Standardmäßig erhält die lokale Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> Zugriff, und die Intranetzone erhält <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> Zugriff.  
  
 In der folgenden Tabelle sind die Funktionen aufgeführt, die auf jeder Druck Berechtigungsebene verfügbar sind.  
  
|PrintingPermissionLevel|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Bietet vollständigen Zugriff auf alle installierten Drucker.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Ermöglicht die programmgesteuerte Druckfunktion auf den Standarddrucker und das sicherere Drucken über ein restriktives Druck Dialogfeld. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Bietet Druck nur in einem Dialogfeld mit eingeschränkter Einschränkung. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Verhindert den Zugriff auf Drucker. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Siehe auch

- [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](more-secure-file-and-data-access-in-windows-forms.md)
- [Weitere Überlegungen zur Sicherheit in Windows Forms](additional-security-considerations-in-windows-forms.md)
- [Übersicht über die Sicherheit in Windows Forms](security-in-windows-forms-overview.md)
- [Sicherheit in Windows Forms](windows-forms-security.md)
