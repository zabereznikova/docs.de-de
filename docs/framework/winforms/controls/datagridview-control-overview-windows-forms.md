---
title: "&#220;bersicht &#252;ber das DataGridView-Steuerelement (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGridView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Gebundene Steuerelemente, DataGridView-Steuerelement"
  - "Spalten [Windows Forms], DataGridView-Steuerelement"
  - "Daten [Windows Forms], Navigieren"
  - "Daten [Windows Forms], Neusortieren"
  - "Datenbindung, DataGridView-Steuerelement"
  - "Datenblätter, Informationen über Datenblätter"
  - "Datenquellen, Binden an das DataGridView-Steuerelement"
  - "DataGridView-Steuerelement [Windows Forms], Informationen über das DataGridView-Steuerelement"
  - "DataGridView-Steuerelement [Windows Forms], Datenbindung"
  - "Datasets [Windows Forms], Binden an das DataGridView-Steuerelement"
  - "Grid-Steuerelemente [Windows Forms]"
  - "Raster [Windows Forms]"
  - "Tabellen [Windows Forms], Binden an das DataGridView-Steuerelement"
  - "Tabellen [Windows Forms], Anzeigen im DataGridView-Steuerelement"
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# &#220;bersicht &#252;ber das DataGridView-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das <xref:System.Windows.Forms.DataGrid>\-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>\-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView\-Steuerelement und dem DataGrid\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie Tabellendaten aus vielen unterschiedlichen Datenquellen anzeigen und bearbeiten.  
  
 Das Binden von Daten an das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist ein unkomplizierter, intuitiver Vorgang und meistens so einfach wie das Festlegen der <xref:System.Windows.Forms.DataGridView.DataSource%2A>\-Eigenschaft.  Beim Binden an eine Datenquelle mit mehreren Listen oder Tabellen legen Sie die <xref:System.Windows.Forms.DataGridView.DataMember%2A>\-Eigenschaft auf eine Zeichenfolge fest, die die Liste oder Tabelle angibt, an die gebunden werden soll.  
  
 Da das <xref:System.Windows.Forms.DataGridView>\-Steuerelement das standardmäßige Windows Forms\-Datenbindungsmodell unterstützt, wird es an Instanzen der in der folgenden Liste beschriebenen Klassen gebunden:  
  
-   Alle Klassen, die die <xref:System.Collections.IList>\-Schnittstelle implementieren, einschließlich eindimensionaler Arrays.  
  
-   Alle Klassen, die die <xref:System.ComponentModel.IListSource>\-Schnittstelle implementieren, z. B. die <xref:System.Data.DataTable>\-Klasse und die <xref:System.Data.DataSet>\-Klasse.  
  
-   Alle Klassen, die die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementieren, z. B. die <xref:System.ComponentModel.BindingList%601>\-Klasse.  
  
-   Alle Klassen, die die <xref:System.ComponentModel.IBindingListView>\-Schnittstelle implementieren, z. B. die <xref:System.Windows.Forms.BindingSource>\-Klasse.  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement unterstützt die Datenbindung an die öffentlichen Eigenschaften der Objekte, die von diesen Schnittstellen zurückgegeben werden, oder an die Eigenschaftenauflistung, die von einer <xref:System.ComponentModel.ICustomTypeDescriptor>\-Schnittstelle zurückgegeben wird, sofern diese für die zurückgegebenen Objekte implementiert wurde.  
  
 Normalerweise führen Sie die Bindung an eine <xref:System.Windows.Forms.BindingSource>\-Komponente aus und binden die <xref:System.Windows.Forms.BindingSource>\-Komponente an eine andere Datenquelle oder füllen diese mit Geschäftsobjekten.  Die <xref:System.Windows.Forms.BindingSource>\-Komponente stellt die bevorzugte Datenquelle dar, da mit dieser Datenquelle Bindungen an eine Vielzahl von Datenquellen vorgenommen werden können und zahlreiche Datenbindungsprobleme automatisch behoben werden.  Weitere Informationen finden Sie unter [BindingSource\-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement kann auch im *Ungebunden*\-Modus ohne zugrunde liegenden Datenspeicher verwendet werden.  Ein Codebeispiel, in dem ein ungebundenes <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet wird, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement ist in hohem Maße konfigurierbar und erweiterbar und stellt zahlreiche Eigenschaften, Methoden und Ereignisse bereit, um sein Aussehen und Verhalten anzupassen.  Zur Anzeige tabellarischer Daten in Windows Forms\-Anwendungen sollten Sie <xref:System.Windows.Forms.DataGridView> den Vorzug vor anderen Steuerelementen geben \(z. B. <xref:System.Windows.Forms.DataGrid>\).  Ob Sie schreibgeschützte Werte in einem kleineren Raster anzeigen oder Benutzern die Bearbeitung einer Tabelle mit Millionen von Datensätzen ermöglichen möchten: das <xref:System.Windows.Forms.DataGridView>\-Steuerelement bietet eine direkt programmierbare, speichereffiziente Lösung.  
  
## In diesem Abschnitt  
 [Zusammenfassung der DataGridView\-Steuerelementtechnologie](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Bietet eine Zusammenfassung der Konzepte des <xref:System.Windows.Forms.DataGridView>\-Steuerelements sowie der Verwendung verwandter Klassen.  
  
 [Architektur des DataGridView\-Steuerelements](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Beschreibt die Architektur des <xref:System.Windows.Forms.DataGridView>\-Steuerelements und erläutert die zugehörige Typhierarchie und Vererbungsstruktur.  
  
 [Szenarien für das DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Beschreibt die häufigsten Szenarien, in denen <xref:System.Windows.Forms.DataGridView>\-Steuerelemente verwendet werden.  
  
 [Codeverzeichnis für DataGridView\-Steuerelementcode](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Enthält Links zu Codebeispielen für verschiedene <xref:System.Windows.Forms.DataGridView>\-Aufgaben in der Dokumentation.  Diese Beispiele sind nach Art der Aufgabe kategorisiert.  
  
## Verwandte Abschnitte  
 [Spaltentypen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Erörtert die Spaltentypen im <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms, die zum Anzeigen von Informationen verwendet werden und Benutzern das Ändern oder Hinzufügen von Informationen ermöglichen.  
  
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen mit Beschreibungen, in denen das Steuerelement entweder manuell oder aus einer externen Datenquelle mit Daten gefüllt wird.  
  
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen das benutzerdefinierte Zeichnen von <xref:System.Windows.Forms.DataGridView>\-Zellen und \-Zeilen sowie das Erstellen abgeleiteter Zell\-, Spalten\- und Zeilentypen beschrieben wird.  
  
 [Leistungsoptimierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Enthält Themen, in denen der effiziente Einsatz des Steuerelements beschrieben wird, um Leistungsprobleme bei der Arbeit mit großen Datenmengen zu vermeiden.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Standardfunktionalität des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)   
 [Standardbehandlung von Tastatur und Maus im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)