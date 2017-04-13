---
title: "Szenarien f&#252;r das DataGridView-Steuerelement (Windows Forms) | Microsoft Docs"
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
  - "Daten [Windows Forms], Anzeigen im tabellarischen Format"
  - "Datenblätter, Informationen über Datenblätter"
  - "DataGridView-Steuerelement [Windows Forms], Szenarien"
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Szenarien f&#252;r das DataGridView-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie Tabellendaten aus einer Vielzahl von Datenquellen anzeigen.  Bei einer einfacheren Verwendungsweise können Sie <xref:System.Windows.Forms.DataGridView> manuell füllen und die Daten direkt über das Steuerelement bearbeiten.  Normalerweise speichern Sie Ihre Daten jedoch in einer externen Datenquelle und binden das Steuerelement über eine <xref:System.Windows.Forms.BindingSource>\-Komponente an die Datenquelle.  
  
 In diesem Thema werden einige häufige Szenarien in Zusammenhang mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement beschrieben.  
  
## Szenario 1: Anzeigen kleinerer Datenmengen  
 Daten müssen nicht in einer externen Datenquelle gespeichert werden, damit sie im <xref:System.Windows.Forms.DataGridView>\-Steuerelement angezeigt werden können.  Bei der Bearbeitung geringerer Datenmengen können Sie diese manuell in das Steuerelement einfügen und die Daten über das Steuerelement bearbeiten.  Dies wird als *Ungebunden\-Modus* bezeichnet.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
### Hauptmerkmale des Szenarios  
  
-   Im Ungebunden\-Modus wird das Steuerelement manuell gefüllt.  
  
-   Der Ungebunden\-Modus ist insbesondere für kleine Mengen schreibgeschützter Daten geeignet.  
  
-   Der Ungebunden\-Modus eignet sich auch für mit Arbeitsblättern vergleichbare oder mit wenig Daten gefüllte Tabellen.  
  
## Szenario 2: Anzeigen und Aktualisieren von in einer externen Datenquelle gespeicherten Daten  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann als Benutzeroberfläche verwendet werden, über die Benutzer auf Daten zugreifen können, die in einer Datenquelle, z. B. einer Datenbanktabelle oder einer Auflistung von Geschäftsobjekten, gespeichert sind.  Weitere Informationen finden Sie unter [Gewusst wie: Binden von Daten an das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
### Hauptmerkmale des Szenarios  
  
-   Im Gebunden\-Modus können Sie eine Verbindung zu einer Datenquelle herstellen, automatisch Spalten auf der Grundlage der Datenquelleneigenschaften oder Datenbankspalten generieren und das Steuerelement anschließend automatisch füllen lassen.  
  
-   Der Gebunden\-Modus ist für die intensive Benutzerinteraktion mit Daten geeignet.  Daten können für die Anzeige formatiert werden, und von Benutzern festgelegte Daten können in das von der Datenquelle erwartete Format analysiert werden.  Formatierungsfehler bei der Dateneingabe und Fehler in Bezug auf Datenbankeinschränkungen können ermittelt werden, sodass Benutzer gewarnt und fehlerhafte Zellen korrigiert werden können.  
  
-   Zusätzliche Funktionen, wie das Sortieren, Fixieren und Neuanordnen von Spalten, ermöglichen es Benutzern, die Anzeige von Daten auf bequeme Weise an ihren Arbeitsablauf anzupassen.  
  
-   Durch die Unterstützung der Zwischenablage können Benutzer Daten aus Ihrer Anwendung in andere Anwendungen kopieren.  
  
## Szenario 3: Erweiterte Daten  
 Bei speziellen, vom standardmäßigen Datenbindungsmodell nicht abgedeckten Anforderungen kann die Interaktion zwischen Steuerelement und Daten durch die Implementierung des *virtuellen Modus* verwaltet werden.  Bei der Implementierung des virtuellen Modus wird mindestens ein Ereignishandler implementiert, über den das Steuerelement Informationen zu Zellen anfordern kann, sobald diese benötigt werden.  
  
 Bei der Verarbeitung umfangreicher Datenmengen wird durch die Implementierung des virtuellen Modus beispielsweise optimale Effizienz gewährleistet.  Der virtuelle Modus eignet sich auch für die Verwaltung der Werte ungebundener Spalten, die zusammen mit aus einer anderen Datenquelle abgerufenen Spalten angezeigt werden.  
  
 Weitere Informationen zum virtuellen Modus finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
### Hauptmerkmale des Szenarios  
  
-   Der virtuelle Modus eignet sich für die Anzeige sehr großer Datenmengen, wenn die Leistung optimiert werden soll.  
  
## Szenario 4: Automatische Größenanpassung bei Zeilen und Spalten  
 Bei der Anzeige von Daten, die regelmäßig aktualisiert werden, können Sie die Größe von Zeilen und Spalten automatisch anpassen und so sicherstellen, dass sämtliche Inhalte sichtbar sind.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement umfasst mehrere Optionen, mit denen die manuelle Größenanpassung aktiviert oder deaktiviert und die Größe zu bestimmten Zeiten programmgesteuert bzw. bei geänderten Inhalten automatisch angepasst werden kann.  Weitere Informationen finden Sie unter [Größenänderungsoptionen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
### Hauptmerkmale des Szenarios  
  
-   Die manuelle Größenanpassung ermöglicht es Benutzern, die Zellhöhe und \-breite festzulegen.  
  
-   Die automatische Größenanpassung ermöglicht es Ihnen, die Zellgröße anzupassen und zu gewährleisten, dass kein Zelleninhalt abgeschnitten wird.  
  
-   Die programmgesteuerte Größenanpassung ermöglicht es Ihnen, die Zellgröße zu bestimmten Zeiten zu ändern und Leistungseinbußen zu vermeiden, die bei einer ständigen automatischen Größenanpassung auftreten.  
  
## Szenario 5: Einfache Anpassung  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet zahlreiche Möglichkeiten, die grundlegende Darstellung und das grundlegende Verhalten zu ändern.  Weitere Informationen finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
### Hauptmerkmale des Szenarios  
  
-   Mithilfe von <xref:System.Windows.Forms.DataGridViewCellStyle>\-Objekten können Sie auf mehreren Ebenen und für einzelne Elemente des Steuerelements Farb\-, Schriftart\-, Formatierungs\- und Positionierungsinformationen angeben.  
  
-   Zellenstile können geschichtet und von mehreren Elementen gemeinsam genutzt werden, was die Wiederverwendung von Code ermöglicht.  
  
## Szenario 6: Erweiterte Anpassung  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet zahlreiche Möglichkeiten, die grundlegende Darstellung und das grundlegende Verhalten anzupassen.  
  
### Hauptmerkmale des Szenarios  
  
-   Sie können eigenen Code zum Zeichnen von Zellen bereitstellen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).  
  
-   Sie können eigenen Code zum Zeichnen von Zeilen bereitstellen.  Dies ist beispielsweise beim Erstellen von Zeilen von Vorteil, deren Inhalt mehrere Spalten umfasst.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Darstellung von Zeilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).  
  
-   Sie können eigene Zell\- und Spaltenklassen implementieren, um die Zelldarstellung anzupassen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen von Zellen und Spalten im DataGridView\-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).  
  
-   Sie können eigene Zell\- und Spaltenklassen implementieren, um andere als die durch die integrierten Spaltentypen bereitgestellten Steuerelemente zu hosten.  Weitere Informationen finden Sie unter [Gewusst wie: Hosten von Steuerelementen in DataGridView\-Zellen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Übersicht über das DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)