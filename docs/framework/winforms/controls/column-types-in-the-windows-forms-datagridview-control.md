---
title: Spaltentypen im DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e45ddcec4459e376a5dab4eec36e51cc2e5e49c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Spaltentypen im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet mehrere Spaltentypen zu Ihr gehörigen Informationen angezeigt und Benutzern ermöglichen, ändern oder Hinzufügen von Informationen.  
  
 Beim Binden einer <xref:System.Windows.Forms.DataGridView> steuern und Festlegen der <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> Eigenschaft, um `true`, Spalten werden automatisch generiert mit Standardspaltentypen entsprechende für die Datentypen, die in die gebundene Datenquelle enthalten sind.  
  
 Auch Instanzen von Klassen Spalte zu erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft. Sie können diese Instanzen für die Verwendung als ungebundene Spalten erstellen, oder Sie können sie manuell binden. Manuell gebundene Spalten sind nützlich, z. B. Wenn Sie eine automatisch generierte Spalte eines bestimmten Typs mit einer Spalte eines anderen Typs ersetzen möchten.  
  
 Die folgende Tabelle beschreibt die verschiedenen Spaltenklassen, die zur Verwendung in der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Mit dem textbasierten verwendet. Beim Binden an Zahlen und Zeichenfolgen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Mit verwendet <xref:System.Boolean> und <xref:System.Windows.Forms.CheckState> Werte. Beim Binden an Werte dieser Typen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Verwendet, um Bilder anzuzeigen. Automatisch generiert, wenn die Bindung an Bytearrays, <xref:System.Drawing.Image> Objekte oder <xref:System.Drawing.Icon> Objekte.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Verwendet, um die Schaltflächen in Zellen angezeigt werden. Beim Binden nicht automatisch generiert. In der Regel verwendet als ungebundene Spalten.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Verwendet, um Dropdownlisten in Zellen angezeigt werden. Beim Binden nicht automatisch generiert. In der Regel datengebundenen Sie von manuell.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Verwendet, um Links in Zellen angezeigt werden. Beim Binden nicht automatisch generiert. In der Regel datengebundenen Sie von manuell.|  
|Ihre benutzerdefinierten Spaltentyp|Sie können eine eigene Spaltenklasse erstellen, durch Vererbung der <xref:System.Windows.Forms.DataGridViewColumn> Klasse oder eines seiner abgeleiteten Klassen, die benutzerdefinierte Darstellung, die Verhalten oder die gehosteten Steuerelemente bereitstellen. Weitere Informationen finden Sie unter [wie: Anpassen von Zellen und Spalten in Windows Forms-DataGridView-Steuerelements durch Erweitern von deren Verhalten und Aussehen](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Diese Spaltentypen werden in den folgenden Abschnitten ausführlicher beschrieben.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 Die <xref:System.Windows.Forms.DataGridViewTextBoxColumn> ist ein allgemeiner Spaltentyp für die Verwendung mit textbasierten-Werten, z. B. Zahlen und Zeichenfolgen. Im Bearbeitungsmodus ein <xref:System.Windows.Forms.TextBox> Steuerelement in der aktiven Zelle angezeigt wird, sodass Benutzer sich der Wert der Zelle zu ändern.  
  
 Zellenwerte werden automatisch in Zeichenfolgen für die Anzeige konvertiert. Werte eingegeben oder vom Benutzer geändert werden automatisch analysiert, um einen Zellenwert des entsprechenden Datentyps zu erstellen. Sie können diese Konvertierungen anpassen, indem die Behandlung der <xref:System.Windows.Forms.DataGridView.CellFormatting> und <xref:System.Windows.Forms.DataGridView.CellParsing> Ereignisse der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Die Zelle Wert Datentyp einer Spalte wird angegeben, der <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> -Eigenschaft der Spalte.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 Die <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> wird verwendet, mit <xref:System.Boolean> und <xref:System.Windows.Forms.CheckState> Werte. <xref:System.Boolean>-Werte werden als zwei oder drei-Status-Kontrollkästchen, abhängig vom Wert der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> Eigenschaft. Wenn die Spalte gebunden ist, um <xref:System.Windows.Forms.CheckState> Werte, die <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> Eigenschaftswert ist `true` standardmäßig.  
  
 In der Regel sind Zellwerte das Kontrollkästchen für die Speicherung, wie alle anderen Daten oder zum Ausführen von Massenvorgängen vorgesehen. Wenn Sie reagieren sofort, wenn Benutzer auf eine Zelle Kontrollkästchen klicken, können Sie behandeln möchten die <xref:System.Windows.Forms.DataGridView.CellClick> Ereignis, aber dieses Ereignis tritt auf, bevor der Wert der Zelle aktualisiert wird. Wenn Sie den neuen Wert zum Zeitpunkt der klicken möchten, ist eine Option zu berechnen, was dem erwarteten Wert basierend auf den aktuellen Wert. Ein anderer Ansatz besteht darin, die Änderung sofort übernehmen und behandeln die <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis, um darauf zu reagieren. Um die Änderung zu übernehmen, wenn die Zelle geklickt wird, müssen Sie behandeln die <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> Ereignis. Wenn die aktuelle Zelle ein Kontrollkästchen-Zelle ist, rufen Sie in den Handler auf, die <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> Methode und übergeben der <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> Wert.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 Die <xref:System.Windows.Forms.DataGridViewImageColumn> wird verwendet, um Bilder anzuzeigen. Image-Spalten können aus einer Datenquelle automatisch aufgefüllt, manuell für ungebundene Spalten aufgefüllt oder dynamisch aufgefüllt werden, in einem Ereignishandler für das <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.  
  
 Die automatische Auffüllung für eine Image-Spalte aus einer Datenquelle mit Bytearrays in verschiedenen Bildformate, einschließlich aller unterstützte Formaten funktioniert die <xref:System.Drawing.Image> Klasse und das OLE-Bild-Format von Microsoft® Access und der Beispieldatenbank Northwind verwendet.  
  
 Eine Image-Spalte manuell zu füllen ist nützlich, wenn Sie die Funktionalität des bereitstellen möchten eine <xref:System.Windows.Forms.DataGridViewButtonColumn>, aber das angepasste aussehen. Sie können behandeln die <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> Ereignis, um auf Klicks in eine Bildzelle zu reagieren.  
  
 Füllen die Zellen der Image-Spalte in einen Handler für das <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis ist nützlich, wenn Sie Bilder für berechnete Werte oder Werte in nicht-Bildformate bereitstellen möchten. Beispielsweise müssen unter Umständen eine Spalte "Risiko" mit Zeichenfolgenwerten wie z. B. `"high"`, `"middle"`, und `"low"` , die als Symbole angezeigt werden soll. Klicken Sie Alternativ können Sie eine "Image"-Spalte enthalten, die die Speicherorte der Bilder enthält, anstatt den Inhalt im Binärformat der Images geladen werden müssen.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewButtonColumn>, können Sie eine Spalte von Zellen, die Schaltflächen anzeigen. Dies ist hilfreich, wenn Sie eine einfache Möglichkeit für Ihre Benutzer zum Ausführen von Aktionen für einzelne Datensätze, z. B. eine Bestellung aufgeben oder Anzeigen von untergeordneten Datensätzen in einem separaten Fenster bereitstellen möchten.  
  
 Schaltflächenspalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Schaltflächenspalten verwenden zu können, müssen Sie diese manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Sie können auf die benutzeraufrufen in Schaltflächenzellen reagieren, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> Ereignis.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, können Sie eine Spalte mit Zellen, die Dropdown-Listenfelder enthalten anzeigen. Dies ist hilfreich für die Dateneingabe in Feldern, die nur bestimmte Werte, z. B. die Category-Spalte der Products-Tabelle in der Northwind-Beispieldatenbank enthalten kann.  
  
 Sie können die Dropdown-Liste verwendet für alle Zellen die gleiche Weise füllen Auffüllen eine <xref:System.Windows.Forms.ComboBox> Dropdown Liste entweder manuell über die zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> -Eigenschaft, oder indem Sie ihn mit einer Datenquelle durch Binden der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> Eigenschaften. Weitere Informationen finden Sie unter [ComboBox-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 Sie können die tatsächlichen Zellenwerte binden, mit der Datenquelle verwendet werden, indem Sie die <xref:System.Windows.Forms.DataGridView> Steuerelement durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> Eigenschaft des der <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Kombinationsfeldspalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Kombinationsfeldspalten verwenden, müssen Sie diese manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewLinkColumn>, können Sie eine Spalte mit Zellen, die Links enthalten anzeigen. Dies ist hilfreich für URL-Werte in der Datenquelle oder als Alternative zu den Schaltflächenspalte für spezielle Verhaltensweisen wie z. B. Öffnen eines Fensters mit untergeordneten Datensätzen.  
  
 Linkspalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Linkspalten zu verwenden, müssen Sie diese manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft.  
  
 Sie können auf Klicks auf Links reagieren, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellContentClick> Ereignis. Dieses Ereignis unterscheidet sich von der <xref:System.Windows.Forms.DataGridView.CellClick> und <xref:System.Windows.Forms.DataGridView.CellMouseClick> Ereignisse, die auftreten, wenn ein Benutzer an einer beliebigen Stelle in einer Zelle klickt.  
  
 Die <xref:System.Windows.Forms.DataGridViewLinkColumn> -Klasse stellt mehrere Eigenschaften zum Ändern der Darstellung des Links vor, während und nach geklickt wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>  
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewImageColumn>  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewLinkColumn>  
 [DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Arbeiten mit Bildspalten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 [Anpassen des DataGridView-Steuerelements von Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
