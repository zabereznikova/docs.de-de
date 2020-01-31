---
title: Grundlagen zum Entwickeln von Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739914"
---
# <a name="windows-forms-control-development-basics"></a>Grundlagen für das Entwickeln von Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement ist eine Klasse, die direkt oder indirekt von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>abgeleitet ist. In der folgenden Liste werden gängige Szenarien zum Entwickeln von Windows Forms-Steuerelementen beschrieben:  
  
- Kombinieren vorhandener Steuerelemente zum Erstellen eines zusammengesetzten Steuer Elements.  
  
     Zusammengesetzte Steuerelemente Kapseln eine Benutzeroberfläche, die als Steuerelement wieder verwendet werden kann. Ein Beispiel für ein zusammengesetztes Steuerelement ist ein Steuerelement, das aus einem Textfeld und einer Schaltfläche Zurücksetzen besteht. Visuelle Designer bieten umfassende Unterstützung für das Erstellen von zusammengesetzten Steuerelementen. Um ein zusammengesetztes Steuerelement zu erstellen, leiten Sie <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>ab. Die Basisklasse <xref:System.Windows.Forms.UserControl> stellt Tastatur Routing für untergeordnete Steuerelemente bereit und ermöglicht es, dass untergeordnete Steuerelemente als Gruppe funktionieren. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md).  
  
- Erweitern eines vorhandenen Steuer Elements, um es anzupassen oder seiner Funktionalität hinzuzufügen.  
  
     Eine Schaltfläche, deren Farbe nicht geändert werden kann, und eine Schaltfläche mit einer zusätzlichen Eigenschaft, die nachverfolgt, wie oft auf Sie geklickt wurde, sind Beispiele für erweiterte Steuerelemente. Sie können jedes Windows Forms Steuerelement anpassen, indem Sie es ableiten und Eigenschaften, Methoden und Ereignisse überschreiben oder hinzufügen.  
  
- Erstellen eines Steuer Elements, das vorhandene Steuerelemente weder kombiniert noch erweitert.  
  
     Leiten Sie in diesem Szenario das Steuerelement von der Basisklasse <xref:System.Windows.Forms.Control>ab. Sie können Eigenschaften, Methoden und Ereignisse der Basisklasse hinzufügen und überschreiben. Informationen zu den ersten Schritten finden Sie unter Gewusst [wie: Entwickeln eines einfachen Windows Forms Steuer](how-to-develop-a-simple-windows-forms-control.md)Elements.  
  
 Die Basisklasse für Windows Forms Steuerelemente, <xref:System.Windows.Forms.Control>, bietet die erforderlichen Maßnahmen für die visuelle Darstellung in Client seitigen Windows-basierten Anwendungen. <xref:System.Windows.Forms.Control> stellt ein Fenster Handle bereit, verarbeitet das Nachrichten Routing und bietet Maus-und Tastatur Ereignisse sowie viele weitere Ereignisse der Benutzeroberfläche. Sie bietet erweiterte Layouts und verfügt über Eigenschaften, die für die visuelle Anzeige spezifisch sind, z. b. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>und viele andere. Außerdem bietet Sie Sicherheit, Threading Unterstützung und Interoperabilität mit ActiveX-Steuerelementen. Da der Großteil der Infrastruktur von der Basisklasse bereitgestellt wird, ist es relativ einfach, Ihre eigenen Windows Forms-Steuerelemente zu entwickeln.  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements](how-to-develop-a-simple-windows-forms-control.md)
- [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](developing-a-composite-windows-forms-control.md)
- [Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Vielfalt benutzerdefinierter Steuerelemente](varieties-of-custom-controls.md)
