---
title: Spaltentypen im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: a33cf4cd865921c04ef10c7fccf3a67c3d22de73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956246"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Spaltentypen im DataGridView-Steuerelement in Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement verwendet mehrere Spaltentypen, die Informationen anzeigen und Benutzern ermöglichen, ändern oder Hinzufügen von Informationen.  
  
 Beim Binden einer <xref:System.Windows.Forms.DataGridView> steuern und Festlegen der <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> Eigenschaft `true`, Spalten werden automatisch generiert, mit Standardspaltentypen für die Datentypen, die in der gebundenen Datenquelle enthalten sind.  
  
 Sie können auch Instanzen aller Spaltenklassen selbst zu erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft. Sie können diese Instanzen für die Verwendung als ungebundene Spalten erstellen, oder Sie können diese manuell binden. Manuell gebundene Spalten sind nützlich, z. B. Wenn Sie eine automatisch generierte Spalte eines bestimmten Typs mit einer Spalte eines anderen Typs ersetzen möchten.  
  
 Die folgende Tabelle beschreibt die verschiedenen Spaltenklassen, die verfügbar sind, für die Verwendung in der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Mit dem textbasierten verwendet. Beim Binden an Zahlen und Zeichenfolgen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Mit verwendet <xref:System.Boolean> und <xref:System.Windows.Forms.CheckState> Werte. Beim Binden an die Werte der folgenden Typen automatisch generiert.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Zum Anzeigen von Bildern verwendet. Automatisch generiert, wenn die Bindung in Bytearrays <xref:System.Drawing.Image> Objekte oder <xref:System.Drawing.Icon> Objekte.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Verwendet in Zellen angezeigt werden sollen. Beim Binden nicht automatisch generiert. In der Regel verwendet als ungebundene Spalten.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Verwendet, um die Dropdownlisten in Zellen angezeigt werden. Beim Binden nicht automatisch generiert. In der Regel datengebundenen Sie von manuell.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Verwendet, um Links in Zellen angezeigt werden. Beim Binden nicht automatisch generiert. In der Regel datengebundenen Sie von manuell.|  
|Ihr benutzerdefinierter Spaltentyp|Sie können eine eigene Spaltenklasse erstellen, durch Vererbung der <xref:System.Windows.Forms.DataGridViewColumn> Klasse oder eines seiner abgeleiteten Klassen, die benutzerdefinierte Darstellung, die Verhalten oder die gehosteten Steuerelemente bereitstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Zellen und Spalten im DataGridView-Steuerelement in Windows Forms durch Erweitern Aussehens und Verhaltens](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)|  
  
 Diese Spaltentypen werden in den folgenden Abschnitten ausführlicher beschrieben.  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 Die <xref:System.Windows.Forms.DataGridViewTextBoxColumn> ist ein allgemeines Spaltentyp für die Verwendung mit einem textbasierten-Werten, z. B. Zahlen und Zeichenfolgen. Im Bearbeitungsmodus eine <xref:System.Windows.Forms.TextBox> in der aktiven Zelle,-Steuerelements angezeigt wird, ermöglicht den Benutzern auf den Zellenwert zu ändern.  
  
 Werte der Zellen werden automatisch in Zeichenfolgen für die Anzeige konvertiert. Werte eingegeben haben, oder vom Benutzer geändert werden automatisch analysiert, um einen Zellenwert des entsprechenden Datentyps zu erstellen. Sie können diese Konvertierungen anpassen, indem die Behandlung der <xref:System.Windows.Forms.DataGridView.CellFormatting> und <xref:System.Windows.Forms.DataGridView.CellParsing> Ereignisse der <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 Der Zellwerttyp Daten einer Spalte wird angegeben, der <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> -Eigenschaft der Spalte.  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 Die <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> wird zusammen mit <xref:System.Boolean> und <xref:System.Windows.Forms.CheckState> Werte. <xref:System.Boolean> Werte anzeigen als zwei oder drei-Status-Kontrollkästchen, abhängig vom Wert der <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> Eigenschaft. Wenn die Spalte gebunden ist, um <xref:System.Windows.Forms.CheckState> Werte, die <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> Eigenschaftswert ist `true` standardmäßig.  
  
 In der Regel dienen Kontrollkästchenzellenwerte für Speicher, wie alle anderen Daten oder für Massenvorgänge. Wenn Sie reagieren, sofort bei der Benutzer auf eine Zelle Kontrollkästchen klicken, können Sie behandeln möchten die <xref:System.Windows.Forms.DataGridView.CellClick> Ereignis, aber dieses Ereignis tritt auf, bevor der Wert der Zelle aktualisiert wird. Wenn Sie den neuen Wert zum Zeitpunkt des Klicks benötigen, wird eine Möglichkeit besteht, zu berechnen, was mit dem erwarteten Wert werden basierend auf den aktuellen Wert. Ein anderer Ansatz ist die Änderung sofort einen Commit auszuführen, und behandeln die <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis, um darauf zu reagieren. Um die Änderung zu übernehmen, wenn die Zelle geklickt wird, müssen Sie behandeln die <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> Ereignis. Wenn die aktuelle Zelle ein Kontrollkästchen ist, rufen Sie in den Handler auf, die <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> -Methode und übergeben Sie die <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> Wert.  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 Die <xref:System.Windows.Forms.DataGridViewImageColumn> wird verwendet, um Bilder anzuzeigen. Image-Spalten können aus einer Datenquelle automatisch aufgefüllt, manuell für ungebundene Spalten aufgefüllt oder dynamisch aufgefüllt werden, in einem Handler für die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis.  
  
 Die automatische Auffüllung des eine Image-Spalte aus einer Datenquelle mit Byte-Arrays in einer Vielzahl von Bildformate, alle von unterstützten Formate wie funktioniert die <xref:System.Drawing.Image> -Klasse und das OLE-Bild-Format, die von Microsoft® Access und der Beispieldatenbank Northwind verwendet.  
  
 Eine Image-Spalte manuell zu füllen ist nützlich, wenn Sie die Funktionalität bereitstellen möchten eine <xref:System.Windows.Forms.DataGridViewButtonColumn>, aber das angepasste aussehen. Sie können behandeln die <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> Ereignis, um auf Klicks in eine Bildzelle reagieren.  
  
 Füllen die Zellen der Image-Spalte in einen Handler für die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis ist hilfreich, wenn Sie Abbilder für berechnete Werte oder Werte in nicht-Bildformate bereitstellen möchten. Angenommen, Sie möglicherweise eine Spalte "Risiko" mit Zeichenfolgenwerten wie z. B. `"high"`, `"middle"`, und `"low"` , die als Symbole angezeigt werden soll. Klicken Sie alternativ müssen Sie eine Spalte "Image" möglicherweise, die die Positionen der Bilder enthält, die statt der binären Inhalt der Bilder geladen werden muss.  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewButtonColumn>, können Sie eine Spalte von Zellen, die Schaltflächen anzeigen. Dies ist nützlich, wenn Sie eine einfache Möglichkeit für Ihre Benutzer zum Ausführen von Aktionen für bestimmte Datensätze, z. B. Bestellung oder Anzeigen von untergeordneten Datensätzen in einem separaten Fenster bereitstellen möchten.  
  
 Schaltflächenspalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Schaltflächenspalten verwenden zu können, müssen sie manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Sie können von Benutzern in Schaltflächenzellen reagieren, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> Ereignis.  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, Sie können anzeigen, eine Spalte von Zellen, die Dropdown-Listenfelder enthalten. Dies ist nützlich für die Dateneingabe in Feldern, die nur bestimmte Werte, z. B. der Kategoriespalte der Products-Tabelle in der Northwind-Beispieldatenbank enthalten kann.  
  
 Sie können die Dropdown-Liste verwendet für alle Zellen die gleiche Weise, die Sie füllen würde Auffüllen eine <xref:System.Windows.Forms.ComboBox> Dropdown Liste entweder manuell über die zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> -Eigenschaft, oder durch deren Bindung an eine Datenquelle über die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>, und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> Eigenschaften. Weitere Informationen finden Sie unter [ComboBox-Steuerelement](combobox-control-windows-forms.md).  
  
 Sie können die Werte des tatsächlichen Zellenwertes binden, mit der Datenquelle ein, die die <xref:System.Windows.Forms.DataGridView> Steuerelement durch Festlegen der <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType>.  
  
 Kombinationsfeld-Box-Spalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Combo Box Spalten verwenden, müssen sie manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft.  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 Mit der <xref:System.Windows.Forms.DataGridViewLinkColumn>, Sie können anzeigen, eine Spalte von Zellen, die Links enthalten. Dies ist nützlich für URL-Werte in der Datenquelle oder alternativ auf die Schaltfläche "-Spalte für bestimmte Verhalten, z. B. Öffnen eines Fensters mit untergeordneten Datensätzen.  
  
 Linkspalten werden nicht automatisch generiert, wenn die Datenbindung einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Um Linkspalten verwenden, müssen sie manuell erstellen und Hinzufügen von zurückgegebene Auflistung der <xref:System.Windows.Forms.DataGridView.Columns%2A> Eigenschaft.  
  
 Sie können auf Klicks auf Links reagieren, durch Behandeln der <xref:System.Windows.Forms.DataGridView.CellContentClick> Ereignis. Dieses Ereignis unterscheidet sich von der <xref:System.Windows.Forms.DataGridView.CellClick> und <xref:System.Windows.Forms.DataGridView.CellMouseClick> Ereignisse, die auftreten, wenn ein Benutzer eine beliebige Stelle in einer Zelle klickt.  
  
 Die <xref:System.Windows.Forms.DataGridViewLinkColumn> Klasse stellt mehrere Eigenschaften bereit, zum Ändern der Darstellung von Links vor, während und nach dem geklickt wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [DataGridView-Steuerelement](datagridview-control-windows-forms.md)
- [Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelement von Windows Forms](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Arbeiten Sie mit Bildspalten im DataGridView-Steuerelement in Windows Forms](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
