---
title: "Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Leistungsoptimierung"
  - "Leistungsoptimierung, Datenblätter"
  - "Leistung, DataGridView-Steuerelement"
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms
Bei der Arbeit mit großen Datenmengen kann das `DataGridView`\-Steuerelement eine erhebliche Belastung des Arbeitsspeichers verursachen und sollte daher mit Bedacht eingesetzt werden.  Auf Clients mit eingeschränkten Speicherkapazitäten kann dieser zusätzliche Speicherbedarf teilweise vermieden werden, indem speicherintensive Features deaktiviert werden.  Außerdem können Sie sämtliche Datenpflege\- und \-abrufvorgänge mithilfe des virtuellen Modus eigenständig verwalten, um die Speichernutzung an Ihr Szenario anzupassen.  
  
## In diesem Abschnitt  
 [Empfohlene Vorgehensweisen für das Skalieren des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie das `DataGridView`\-Steuerelement eingesetzt wird, um die unnötige Speichernutzung sowie Leistungseinbußen bei der Arbeit mit umfangreichen Datenmengen zu vermeiden.  
  
 [Virtueller Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Beschreibt, wie der virtuelle Modus verwendet wird, um den standardmäßigen Datenbindungsmechanismus zu ergänzen oder zu ersetzen.  
  
 [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Beschreibt, wie Handler für einige Ereignisse im virtuellen Modus implementiert werden.  Veranschaulicht ebenfalls, wie Rollbacks auf Zeilenebene und Commits für Benutzerbearbeitungen implementiert werden.  
  
 [Implementieren des virtuellen Modus mit Just\-In\-Time\-Laden von Daten in das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Beschreibt das Laden von Daten bei Bedarf – ein hilfreiches Feature, wenn mehr Daten angezeigt werden müssen, als vom verfügbaren Clientspeicher aufgenommen werden können.  
  
## Referenz  
 <xref:System.Windows.Forms.DataGridView>  
 Enthält die Referenzdokumentation zum <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Enthält die Referenzdokumentation zur <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>\-Eigenschaft.  
  
## Siehe auch  
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)