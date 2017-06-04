---
title: "Gr&#246;&#223;enanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Spalten [Windows Forms], Größenänderung in Datenblättern"
  - "Datenblätter, Größenänderung von Spalten und Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Größenanpassung von Zeilen und Spalten"
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gr&#246;&#223;enanpassung bei Spalten und Zeilen im DataGridView-Steuerelement in Windows Forms
Das `DataGridView`\-Steuerelement stellt zahlreiche Optionen bereit, mit denen das Größenanpassungsverhalten seiner Spalten und Zeilen angepasst werden kann.  Die Größenänderung von `DataGridView`\-Zellen basiert normalerweise nicht auf deren Inhalt.  Stattdessen wird jeder Anzeigewert, der über die Zelle hinausgeht, abgeschnitten.  Wenn der Inhalt als Zeichenfolge dargestellt werden kann, wird er von der Zelle in einer QuickInfo angezeigt.  
  
 Der Benutzer kann standardmäßig Zeilen\-, Spalten\- und Headerunterteiler mit der Maus ziehen, um weitere Informationen anzuzeigen.  Darüber hinaus kann ein Benutzer auch auf einen Unterteiler doppelklicken, um die Größe des damit verknüpften Zeilen\-, Spalten\- oder Headerbands auf der Grundlage des Inhalts automatisch zu ändern.  
  
 Das `DataGridView`\-Steuerelement umfasst Eigenschaften, Methoden und Ereignisse, mit deren Hilfe Sie alle diese benutzergesteuerten Verhaltensweisen anpassen oder deaktivieren können.  Darüber hinaus können Sie die Größe von Zeilen, Spalten und Headern programmgesteuert an deren Inhalt anpassen oder so konfigurieren, dass sie ihre Größe automatisch ändern, sobald sich der Inhalt ändert.  Sie können die Spalten auch so konfigurieren, dass die verfügbare Breite des Steuerelements automatisch entsprechend festgelegter Proportionen aufgeteilt wird.  
  
## In diesem Abschnitt  
 [Größenänderungsoptionen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 Beschreibt die Optionen für die Größenanpassung bei Zeilen, Spalten und Headern.  Enthält auch ausführliche Informationen zu Eigenschaften und Methoden für die Größenanpassung sowie Szenarien zur allgemeinen Verwendung.  
  
 [Spaltenfüllmodus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 Enthält eine ausführliche Beschreibung des Spaltenfüllmodus und bietet Beispielcode, um den Spaltenfüllmodus und andere Modi in verschiedenen Szenarien durchzuspielen.  
  
 [Gewusst wie: Festlegen der Größenanpassungsmodi des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie die Größenanpassungsmodi für allgemeine Zwecke konfiguriert werden.  
  
 [Gewusst wie: Programmgesteuertes Anpassen der Zellengröße an den Inhalt im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 Stellt Beispielcode bereit, den Sie verwenden können, um Szenarien der programmgesteuerten Größenanpassung durchzuspielen.  
  
 [Gewusst wie: Automatisches Anpassen der Zellengröße bei Änderungen des Inhalts im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 Stellt Beispielcode bereit, den Sie verwenden können, um Szenarien für die automatischen Größenanpassungsmodi durchzuspielen.  
  
## Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation zum <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  
  
## Siehe auch  
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)