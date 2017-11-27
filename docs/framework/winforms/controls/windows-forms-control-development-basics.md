---
title: "Grundlagen für das Entwickeln von Windows Forms-Steuerelementen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca2bac983e25ab7453230a6718fe7eaa98e82275
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-control-development-basics"></a>Grundlagen für das Entwickeln von Windows Forms-Steuerelementen
Ein Windows Forms-Steuerelement ist eine Klasse, die direkt oder indirekt abgeleitet <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Die folgende Liste beschreibt allgemeine Szenarien für die Entwicklung von Windows Forms-Steuerelemente:  
  
-   Erstellen ein zusammengesetztes Steuerelements kombinieren vorhandener gesteuert werden.  
  
     Zusammengesetzte Steuerelemente kapseln eine Benutzeroberfläche, die als Steuerelement wiederverwendet werden kann. Ein Beispiel für ein zusammengesetztes Steuerelement ist ein Steuerelement, das aus einem Textfeld und einer Schaltfläche "Zurücksetzen" besteht. Visuelle Designer bieten umfangreiche Unterstützung für das Erstellen von zusammengesetzten Steuerelementen. Zum Erstellen eines zusammengesetzten Steuerelements abgeleitet <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. Die Basisklasse <xref:System.Windows.Forms.UserControl> stellt Tastaturrouting für die untergeordneten Steuerelemente und ermöglicht untergeordneten Steuerelementen in einer Gruppe zu arbeiten. Weitere Informationen finden Sie unter [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Erweitern Sie ein vorhandenes Steuerelement, um ihn anzupassen oder seine Funktionalität hinzufügen.  
  
     Eine Schaltfläche, deren Farbe nicht geändert werden kann, und eine Schaltfläche, die eine zusätzliche Eigenschaft besitzt, die verfolgt, wie oft geklickt wurde sind Beispiele für erweiterte Steuerelemente. Sie können jedes Windows Forms-Steuerelement anpassen, indem Sie daraus ableiten und außer Kraft setzen oder Hinzufügen von Eigenschaften, Methoden und Ereignisse.  
  
-   Erstellen eines Steuerelements, das nicht der Fall ist, erweitern Sie vorhandene Steuerelemente oder kombinieren.  
  
     In diesem Szenario leiten Sie das Steuerelement von der Basisklasse <xref:System.Windows.Forms.Control>. Sie können hinzufügen sowie Eigenschaften, Methoden und Ereignisse der Basisklasse zu überschreiben. Um zu beginnen, finden Sie unter [Vorgehensweise: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 Die Basisklasse für Windows Forms-Steuerelemente <xref:System.Windows.Forms.Control>, bietet die Grundlagen für die visuelle Darstellung in einer clientseitigen Windows-basierten Anwendungen erforderlich sind. <xref:System.Windows.Forms.Control>Stellt ein Fensterhandle, das Nachrichtenrouting verarbeitet und ermöglicht das Maus-und Tastaturereignissen sowie viele andere Benutzer Schnittstellenereignissen. Es bietet ein erweitertes Layout und verfügt über Eigenschaften, die für die visuelle Anzeige, z. B. <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, und viele andere. Darüber hinaus bietet sie Sicherheit threading-Unterstützung und Interoperabilität mit ActiveX-Steuerelemente. Da der Großteil der Infrastruktur von der Basisklasse bereitgestellt wird, ist es relativ einfach, Ihre eigenen Windows Forms-Steuerelemente zu entwickeln.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Entwickeln eines zusammengesetzten Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
