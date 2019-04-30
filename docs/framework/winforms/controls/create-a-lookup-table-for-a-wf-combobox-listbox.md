---
title: 'Vorgehensweise: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: a58522cc17ac379897a89a8e61485a1e271438a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011470"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Vorgehensweise: Erstellen einer Suchtabelle für ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows Forms
Manchmal ist es sinnvoll, Daten in einem benutzerfreundlichen Format in einem Windows Form anzuzeigen, aber Sie sollten die Daten in einem Format speichern, das vor allem für Ihr Programm sinnvoll ist. Beispielsweise können in einem Bestellformular für Nahrungsmittel die Menüelemente nach Namen in einem Listenfeld angezeigt werden. Die zur Erfassung der Bestellung verwendete Datentabelle enthält hingegen die eindeutigen ID-Nummern der Nahrungsmittel. Die folgende Tabelle enthält ein Beispiel zum Speichern und Anzeigen von Bestellformulardaten für Nahrungsmittel.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Menge|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|Name|  
|--------|----------|  
|12|Kartoffel|  
|13|Huhn|  
  
 In diesem Szenario wird eine Tabelle, **OrderDetailsTable**, speichert die tatsächlichen Informationen, die Sie befürchten angezeigt und gespeichert. Allerdings geschieht dies aus Platzgründen auf eine ziemlich kryptische Art und Weise. Die andere Tabelle, **ItemTable**, enthält nur darstellungsbezogene Informationen, welche ID-Nummer der Name des Nahrungsmittels und nichts über die tatsächlichen Food-Aufträge entspricht.  
  
 Die **ItemTable** verbunden ist, um die <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, oder <xref:System.Windows.Forms.CheckedListBox> durch drei Eigenschaften. Die `DataSource` Eigenschaft enthält den Namen dieser Tabelle. Die `DisplayMember` Eigenschaft enthält die Datenspalte dieser Tabelle, die im Steuerelement (der Name des Nahrungsmittels) angezeigt werden soll. Die `ValueMember` Eigenschaft enthält die Datenspalte der Tabelle mit den gespeicherten Informationen (die ID-Nummer).  
  
 Die **OrderDetailsTable** an das Steuerelement verbunden ist, die von der bindungsauflistung, der Zugriff erfolgt über die <xref:System.Windows.Forms.Control.DataBindings%2A> Eigenschaft. Wenn Sie auf die Auflistung ein Bindungsobjekt hinzufügen, verbinden Sie eine Steuerelementeigenschaft zu einem bestimmten Datenmember (die Spalte von ID-Nummern) in einer Datenquelle (die **OrderDetailsTable**). Wenn im Steuerelement eine Auswahl getroffen wird, wird die Formulareingabe in dieser Tabelle gespeichert.  
  
### <a name="to-create-a-lookup-table"></a>So erstellen Sie eine Suchtabelle  
  
1. Fügen Sie dem Formular ein Steuerelement "<xref:System.Windows.Forms.ComboBox>", "<xref:System.Windows.Forms.ListBox>", oder "<xref:System.Windows.Forms.CheckedListBox>" hinzu.  
  
2. Stellen Sie eine Verbindung zur Datenquelle her.  
  
3. Richten Sie eine Datenbeziehung zwischen den beiden Tabellen ein. Finden Sie unter [Einführung in DataRelation-Objekte](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).  
  
4. Legen Sie die folgenden Eigenschaften fest. Sie können im Code oder im Designer festgelegt werden.  
  
    |Eigenschaft|Einstellung|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Die Tabelle, die Informationen darüber enthält, welche ID-Nummer welchem Element entspricht. Im vorherigen Szenario ist dies `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|Die Spalte der Datenquellentabelle, die im Steuerelement angezeigt werden soll. Im vorherigen Szenario ist dies `"Name"` (um im Code festzulegen, verwenden Sie Anführungszeichen).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|Die Spalte der Datenquellentabelle, die die gespeicherten Informationen enthält. Im vorherigen Szenario ist dies `"ID"` (um im Code festzulegen, verwenden Sie Anführungszeichen).|  
  
5. Rufen Sie in einer Prozedur die Methode "<xref:System.Windows.Forms.ControlBindingsCollection.Add%2A>" der Klasse "<xref:System.Windows.Forms.ControlBindingsCollection>" auf, um die Eigenschaft "<xref:System.Windows.Forms.ListControl.SelectedValue%2A>" des Steuerelements an die Tabelle zu binden, die die Formulareingabe erfasst. Sie können hierzu auch im Designer statt im Code durch den Zugriff auf des Steuerelements des <xref:System.Windows.Forms.Control.DataBindings%2A> -Eigenschaft in der **Eigenschaften** Fenster. Im vorherigen Szenario ist dies `OrderDetailsTable`, und die Spalte `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung und Windows Forms](../data-binding-and-windows-forms.md)
- [Übersicht über das ListBox-Steuerelement](listbox-control-overview-windows-forms.md)
- [Übersicht über das ComboBox-Steuerelement](combobox-control-overview-windows-forms.md)
- [Übersicht über das CheckedListBox-Steuerelement](checkedlistbox-control-overview-windows-forms.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
