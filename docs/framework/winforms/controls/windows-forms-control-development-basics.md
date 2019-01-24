---
title: Grundlagen für das Entwickeln von Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: b40c45905c65cdc40d77553a93e83aa417199826
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643553"
---
# <a name="windows-forms-control-development-basics"></a>Grundlagen für das Entwickeln von Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement ist eine Klasse, die direkt oder indirekt von abgeleitet <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Die folgende Liste beschreibt allgemeine Szenarien für die Entwicklung von Windows Forms-Steuerelemente:  
  
-   Kombinieren von vorhandenen steuert, um ein zusammengesetztes Steuerelement zu erstellen.  
  
     Zusammengesetzte Steuerelemente kapseln eine Benutzeroberfläche, die als Steuerelement wiederverwendet werden kann. Ein Beispiel für ein zusammengesetztes Steuerelement ist ein Steuerelement, das aus einem Textfeld und eine Schaltfläche "Zurücksetzen" besteht. Visuelle Designer bieten umfassende Unterstützung für das Erstellen von zusammengesetzter Steuerelementen. Um ein zusammengesetztes Steuerelement zu erstellen, leiten Sie von <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. Die Basisklasse <xref:System.Windows.Forms.UserControl> stellt Tastaturrouting für die untergeordneten Steuerelemente und untergeordnete Steuerelemente als Gruppe arbeiten kann. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Erweitern Sie ein vorhandenes Steuerelement anpassen oder ihre Funktionalität hinzufügen.  
  
     Eine Schaltfläche, deren Farbe nicht geändert werden kann, und eine Schaltfläche, die eine zusätzliche Eigenschaft, die Häufigkeit verfolgt sie bereits geklickt wurde, verfügt über sind Beispiele der erweiterten Steuerelemente. Sie können jedes Windows Forms-Steuerelement anpassen, indem abgeleitet wird, und überschreiben oder Hinzufügen von Eigenschaften, Methoden und Ereignisse.  
  
-   Erstellen ein Steuerelement, das nicht der Fall ist, erweitern Sie vorhandene Steuerelemente oder kombinieren.  
  
     In diesem Szenario leiten Sie das Steuerelement von der Basisklasse <xref:System.Windows.Forms.Control>. Sie können hinzufügen sowie Eigenschaften, Methoden und Ereignisse der Basisklasse zu überschreiben. Informationen zum Einstieg finden Sie unter [Vorgehensweise: Entwickeln ein einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 Die Basisklasse für Windows Forms-Steuerelemente, <xref:System.Windows.Forms.Control>, bietet die Grundlagen für die grafische Darstellung in clientseitigen Windows-basierten Anwendungen erforderlich sind. <xref:System.Windows.Forms.Control> bietet ein Fensterhandle, das Nachrichtenrouting verarbeitet, sowie Maus-und Tastaturereignissen sowie viele andere Ereignisse der Benutzeroberfläche. Es bietet ein erweitertes Layout und verfügt über Eigenschaften, die für die visuelle Anzeige, z. B. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, und viele andere. Darüber hinaus bietet sie Sicherheit, threading-Unterstützung und Interoperabilität mit ActiveX-Steuerelementen. Da der Großteil der Infrastruktur von der Basisklasse bereitgestellt wird, ist es relativ einfach, Ihre eigenen Windows Forms-Steuerelemente zu entwickeln.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)
- [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)
- [Vorgehensweise: Erstellen Sie ein Windows Forms-Steuerelement, das ausgeführt wird.](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
