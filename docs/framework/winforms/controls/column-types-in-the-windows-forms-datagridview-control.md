---
title: "Spaltentypen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Typen"
  - "Datenblätter, Spalten"
  - "DataGridView-Steuerelement [Windows Forms], Spaltentypen"
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Spaltentypen im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet verschiedene Spaltentypen, um deren Inhalt anzuzeigen und es Benutzern zu ermöglichen, Informationen zu ändern oder hinzuzufügen.  
  
 Wenn Sie ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement binden und die <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>\-Eigenschaft auf `true` festlegen, werden Spalten automatisch anhand von standardmäßigen Spaltentypen generiert, die für die in der gebundenen Datenquelle enthaltenen Datentypen geeignet sind.  
  
 Sie können auch selbst Instanzen der Spaltenklassen erstellen und sie der von der <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Eigenschaft zurückgegebenen Auflistung hinzufügen.  Sie können diese Instanzen zur Verwendung als ungebundene Spalten erstellen oder sie manuell binden.  Manuell gebundene Spalten sind beispielsweise hilfreich, wenn Sie eine automatisch generierte Spalte eines bestimmten Typs durch eine Spalte eines anderen Typs ersetzen möchten.  
  
 In der folgenden Tabelle werden die verschiedenen Spaltenklassen beschrieben, die im <xref:System.Windows.Forms.DataGridView>\-Steuerelement verfügbar sind.  
  
|Klasse|Beschreibung|  
|------------|------------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Wird mit textbasierten Werten verwendet.  Wird beim Binden an Zahlen und Zeichenfolgen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Wird mit <xref:System.Boolean>\-Werten und <xref:System.Windows.Forms.CheckState>\-Werten verwendet.  Wird beim Binden an Werte dieser Typen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Wird zur Anzeige von Bildern verwendet.  Wird beim Binden an Bytearrays, <xref:System.Drawing.Image>\-Objekte oder <xref:System.Drawing.Icon>\-Objekte automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Wird zur Anzeige von Schaltflächen in Zellen verwendet.  Wird beim Binden nicht automatisch generiert.  Wird normalerweise als ungebundene Spalte verwendet.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Wird zur Anzeige von Dropdownlisten in Zellen verwendet.  Wird beim Binden nicht automatisch generiert.  Wird normalerweise manuell an Daten gebunden.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Wird zur Anzeige von Links in Zellen verwendet.  Wird beim Binden nicht automatisch generiert.  Wird normalerweise manuell an Daten gebunden.|  
|Der benutzerdefinierte Spaltentyp|Sie können eine eigene Spaltenklasse erstellen, indem Sie die <xref:System.Windows.Forms.DataGridViewColumn>\-Klasse oder eine ihrer abgeleiteten Klassen erben, um benutzerdefiniertes Aussehen, Verhalten oder gehostete Steuerelemente bereitzustellen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen von Zellen und Spalten im DataGridView\-Steuerelement in Windows Forms durch Erweitern des Aussehens und Verhaltens](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Diese Spaltentypen werden in den folgenden Abschnitten ausführlich beschrieben.  
  
## DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> ist ein allgemeiner Spaltentyp für textbasierte Werte wie Zahlen und Zeichenfolgen.  Im Bearbeitungsmodus wird ein <xref:System.Windows.Forms.TextBox>\-Steuerelement in der aktiven Zelle angezeigt, sodass die Benutzer den Zellenwert ändern können.  
  
 Zellenwerte werden zur Anzeige automatisch in Zeichenfolgen konvertiert.  Vom Benutzer eingegebene oder geänderte Werte werden automatisch analysiert, um einen Zellenwert des entsprechenden Datentyps zu erstellen.  Sie können diese Konvertierungen anpassen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis und <xref:System.Windows.Forms.DataGridView.CellParsing>\-Ereignis des <xref:System.Windows.Forms.DataGridView>\-Steuerelements behandeln.  
  
 Der Zellenwertdatentyp einer Spalte wird in der <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A>\-Eigenschaft der Spalte angegeben.  
  
## DataGridViewCheckBoxColumn  
 Der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> wird mit dem <xref:System.Boolean>\-Wert und dem <xref:System.Windows.Forms.CheckState>\-Wert verwendet.  <xref:System.Boolean>\-Werte werden als Kontrollkästchen mit zwei oder drei Zustanden angezeigt, je nach Wert der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>\-Eigenschaft.  Wenn die Spalte an <xref:System.Windows.Forms.CheckState>\-Werte gebunden ist, lautet der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>\-Eigenschaftswert standardmäßig `true`.  
  
 Für gewöhnlich dienen Kontrollkästchenzellenwerte entweder zum Speichern, ebenso wie andere Daten, oder zum Ausführen von Sammeloperationen.  Wenn Sie unmittelbar darauf reagieren möchten, wenn Benutzer auf eine Kontrollkästchenzelle klicken, können Sie das <xref:System.Windows.Forms.DataGridView.CellClick>\-Ereignis behandeln. Dieses Ereignis tritt jedoch vor einer Aktualisierung des Zellwerts auf.  Wenn Sie den neuen Wert zur Zeit des Klickens benötigen, kann der erwartete Wert z. B. mithilfe des aktuellen Werts berechnet werden.  Es besteht auch die Möglichkeit, sofort einen Commit für die Änderung auszuführen und das <xref:System.Windows.Forms.DataGridView.CellValueChanged>\-Ereignis zu behandeln, um darauf zu antworten.  Um für die Änderung einen Commit auszuführen, wenn auf die Zelle geklickt wurde, muss das <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>\-Ereignis behandelt werden.  Wenn die aktuelle Zelle eine Kontrollkästchenzelle ist, rufen Sie im Handler die <xref:System.Windows.Forms.DataGridView.CommitEdit%2A>\-Methode auf, und übergeben Sie den <xref:System.Windows.Forms.DataGridViewDataErrorContexts>\-Wert.  
  
## DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn> wird zur Anzeige von Bildern verwendet.  Bildspalten können wie folgt gefüllt werden: automatisch aus einer Datenquelle, manuell für ungebundene Spalten oder dynamisch in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis.  
  
 Das automatische Füllen einer Bildspalte aus einer Datenquelle kann mit Bytearrays in verschiedenen Bildformaten erfolgen, einschließlich aller von der <xref:System.Drawing.Image>\-Klasse unterstützen Formate und dem von Microsoft® Access und der Beispieldatenbank Northwind verwendeten OLE Picture\-Format.  
  
 Eine Bildspalte manuell zu füllen bietet sich an, wenn Sie die Funktionalität einer <xref:System.Windows.Forms.DataGridViewButtonColumn> bereitstellen, aber das Aussehen anpassen möchten.  Sie können das <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>\-Ereignis behandeln, um auf Klicks in eine Bildzelle zu reagieren.  
  
 Das Füllen von Zellen einer Bildspalte in einem Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis ist hilfreich, wenn Sie Bilder für berechnete Werte oder Werte in einem anderen Format als einem Bildformat bereitstellen möchten.  Möglicherweise verfügen Sie über eine Risikospalte mit den Zeichenfolgenwerten `"high"`, `"middle"` und `"low"`, die Sie als Symbole anzeigen möchten.  Denkbar ist auch, dass Sie über eine Bildspalte verfügen, die anstelle des binären Inhalts der Bilder die Speicherorte von Bildern enthält, die geladen werden müssen.  
  
## DataGridViewButtonColumn  
 Mit <xref:System.Windows.Forms.DataGridViewButtonColumn> können Sie eine Spalte mit Zellen anzeigen, die Schaltflächen enthalten.  Dies bietet sich an, wenn Sie Benutzern die Möglichkeit geben möchten, Aktionen zu bestimmten Datensätzen auf einfache Weise auszuführen, z. B. das Erteilen eines Auftrags oder das Anzeigen von untergeordneten Datensätzen in einem separaten Fenster.  
  
 Schaltflächenspalten werden bei der Datenbindung eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements nicht automatisch generiert.  Um Schaltflächenspalten verwenden zu können, müssen Sie sie manuell erstellen und der von der <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>\-Eigenschaft zurückgegebenen Auflistung hinzufügen.  
  
 Sie können auf das Klicken in Schaltflächenzellen reagieren, indem Sie das <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>\-Ereignis behandeln.  
  
## DataGridViewComboBoxColumn  
 Mit <xref:System.Windows.Forms.DataGridViewComboBoxColumn> können Sie eine Spalte mit Zellen anzeigen, die Dropdown\-Listenfelder enthalten.  Dies ist für die Dateneingabe in Felder geeignet, die nur bestimmte Werte enthalten können, z. B. die Spalte Category der Tabelle Products in der Beispieldatenbank Northwind.  
  
 Sie können die für alle Zellen verwendete Dropdownliste auf die gleiche Weise füllen wie eine <xref:System.Windows.Forms.ComboBox>\-Dropdownliste, d. h. entweder manuell mit der von der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>\-Eigenschaft zurückgegebenen Auflistung oder durch Binden an eine Datenquelle mithilfe der Eigenschaften <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.  Weitere Informationen finden Sie unter [ComboBox\-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 Sie können die eigentlichen Zellenwerte an die vom <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendete Datenquelle binden, indem Sie die <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A>\-Eigenschaft der <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName> festlegen.  
  
 Kombinationsfeldspalten werden bei der Datenbindung eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements nicht automatisch generiert.  Um Kombinationsfeldspalten verwenden zu können, müssen Sie sie manuell erstellen und der von der <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Eigenschaft zurückgegebenen Auflistung hinzufügen.  
  
## DataGridViewLinkColumn  
 Mit <xref:System.Windows.Forms.DataGridViewLinkColumn> können Sie eine Spalte mit Zellen anzeigen, die Links enthalten.  Dies bietet sich an, wenn die Datenquelle URL\-Werte enthält, oder aber als Alternative zur Schaltflächenspalte für bestimmte Verhalten wie das Öffnen eines Fensters mit untergeordneten Datensätzen.  
  
 Linkspalten werden bei der Datenbindung eines <xref:System.Windows.Forms.DataGridView>\-Steuerelements nicht automatisch generiert.  Um Linkspalten verwenden zu können, müssen Sie sie manuell erstellen und der von der <xref:System.Windows.Forms.DataGridView.Columns%2A>\-Eigenschaft zurückgegebenen Auflistung hinzufügen.  
  
 Sie können auf Klicks auf Links reagieren, indem Sie das <xref:System.Windows.Forms.DataGridView.CellContentClick>\-Ereignis behandeln.  Dieses Ereignis unterscheidet sich vom <xref:System.Windows.Forms.DataGridView.CellClick>\-Ereignis und <xref:System.Windows.Forms.DataGridView.CellMouseClick>\-Ereignis, die auftreten, sobald ein Benutzer auf eine beliebige Stelle in einer Zelle klickt.  
  
 Die <xref:System.Windows.Forms.DataGridViewLinkColumn>\-Klasse stellt mehrere Eigenschaften zum Ändern der Darstellung von Links vor, bei und nach dem Klicken bereit.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewButtonColumn>   
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewImageColumn>   
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewLinkColumn>   
 [DataGridView\-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Arbeiten mit Bildspalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)   
 [Anpassen des DataGridView\-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)