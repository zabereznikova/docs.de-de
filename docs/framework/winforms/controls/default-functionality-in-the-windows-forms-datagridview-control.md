---
title: "Standardfunktionalit&#228;t des DataGridView-Steuerelements von Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Standardfunktionen im DataGridView-Steuerelement"
  - "DataGridView-Steuerelement [Windows Forms], Standardfunktionen"
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Standardfunktionalit&#228;t des DataGridView-Steuerelements von Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms bietet Benutzern ein erhebliches Maß an Standardfunktionalität.  
  
## Standardfunktionalität  
 Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügt standardmäßig über folgende Funktionen:  
  
-   Automatische Anzeige von Spalten\- und Zeilenheader, die bei vertikalem Bildlauf der Tabelle sichtbar bleiben  
  
-   Zeilenheader mit einem Auswahlindikator für die aktuelle Zeile  
  
-   Auswahlrechteck in der ersten Zelle  
  
-   Spalten, deren Größe mit einem Doppelklick auf den Spaltenunterteiler automatisch angepasst werden kann  
  
-   Automatische Unterstützung von visuellen Stilen unter Windows XP und Windows Server 2003, wenn die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>\-Methode in der `Main`\-Methode der Anwendung aufgerufen wird.  
  
 Der Inhalt eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements kann zudem standardmäßig bearbeitet werden:  
  
-   Wenn der Benutzer in einer Zelle doppelklickt oder die Taste F2 drückt, aktiviert das Steuerelement automatisch den Bearbeitungsmodus für die Zelle und aktualisiert den Inhalt der Zelle während der Eingabe.  
  
-   Am Ende des Datenblatts wird eine zusätzliche Zeile zum Hinzufügen neuer Datensätze angezeigt.  Wenn der Benutzer auf diese Zeile klickt, wird dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement eine neue Zeile hinzugefügt.  Durch Drücken der Taste ESC wird diese neue Zeile wieder gelöscht.  
  
-   Wenn der Benutzer auf einen Zeilenheader klickt, wird die gesamte Zeile ausgewählt.  
  
 Wenn Sie ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine Datenquelle binden, indem Sie dessen <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft festlegen, erhält das Steuerelement folgende Funktionalität:  
  
-   Automatische Verwendung der Spaltennamen der Datenquelle als Spaltenheadertext  
  
-   Füllung mit dem Inhalt der Datenquelle.  Für die einzelnen Spalten der Datenquelle werden automatisch <xref:System.Windows.Forms.DataGridView>\-Spalten erstellt.  
  
-   Automatische Erstellung einer Zeile für jede sichtbare Zeile der Tabelle  
  
-   Wenn der Benutzer auf einen Spaltenheader klickt, werden die Zeilen automatisch nach den zugrunde liegenden Daten sortiert.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)