---
title: "Gewusst wie: Erstellen einer Suchtabelle f&#252;r ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows&#160;Forms | Microsoft Docs"
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
  - "CheckedListBox-Steuerelement [Windows Forms], Erstellen von Nachschlagetabellen"
  - "Kombinationsfelder, Suchtabellen"
  - "ComboBox-Steuerelement [Windows Forms], Suchtabelle"
  - "Listenfelder, Suchtabellen"
  - "ListBox-Steuerelement [Windows Forms], Erstellen von Nachschlagetabellen"
  - "ListBox-Steuerelement [Windows Forms], Suchtabellen"
  - "Suchtabellen"
  - "Suchtabellen, Erstellen für Steuerelemente"
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erstellen einer Suchtabelle f&#252;r ComboBox-, ListBox- oder CheckedListBox-Steuerelemente in Windows&#160;Forms
Manchmal ist es sinnvoll, Daten in einem benutzerfreundlichen Format in einem Windows Form anzuzeigen, aber Sie sollten die Daten in einem Format speichern, das vor allem für Ihr Programm sinnvoll ist.  Beispielsweise können in einem Bestellformular für Nahrungsmittel die Menüelemente nach Namen in einem Listenfeld angezeigt werden.  Die zur Erfassung der Bestellung verwendete Datentabelle enthält hingegen die eindeutigen ID\-Nummern der Nahrungsmittel.  Die folgende Tabelle enthält ein Beispiel zum Speichern und Anzeigen von Bestellformulardaten für Nahrungsmittel.  
  
### OrderDetailsTable  
  
|OrderID|ItemID|Menge|  
|-------------|------------|-----------|  
|4085|12|1|  
|4086|13|3|  
  
### ItemTable  
  
|ID|Name|  
|--------|----------|  
|12|Kartoffel|  
|13|Huhn|  
  
 In diesem Szenario werden die anzuzeigenden und zu speichernden Informationen in der Tabelle "OrderDetailsTable" gespeichert.  Allerdings geschieht dies aus Platzgründen auf eine ziemlich kryptische Art und Weise.  Die andere Tabelle, "ItemTable", enthält nur darstellungsbezogene Informationen darüber, welche ID\-Nummer welchem Nahrungsmittelnamen entspricht. Informationen zu den Nahrungsmittelbestellungen enthält diese Tabelle nicht.  
  
 Die Tabelle "ItemTable" ist durch drei Eigenschaften mit dem Steuerelement "<xref:System.Windows.Forms.ComboBox>", "<xref:System.Windows.Forms.ListBox>" oder "<xref:System.Windows.Forms.CheckedListBox>" verbunden.  Die Eigenschaft " `DataSource` " enthält den Namen dieser Tabelle.  Die Eigenschaft " `DisplayMember`" enthält die Datenspalte dieser Tabelle, die im Steuerelement anzeigt werden soll{b\> \<b}\(der Name des Nahrungsmittels\).  Die Eigenschaft " `ValueMember` " enthält die Datenspalte der Tabelle mit den gespeicherten Informationen \(der ID\-Nummer\).  
  
 Die Tabelle "OrderDetailsTable" ist über ihre Bindungsauflistung mit dem Steuerelement verbunden, und der Zugriff auf die Bindungsauflistung erfolgt über die Eigenschaft "<xref:System.Windows.Forms.Control.DataBindings%2A>".  Wenn Sie der Auflistung ein Bindungsobjekt hinzufügen, verbinden Sie eine Steuerelementeigenschaft mit einem bestimmten Datenelement \(Spalte mit den ID\-Nummern\) in einer Datenquelle \(OrderDetailsTable\).  Wenn im Steuerelement eine Auswahl getroffen wird, wird die Formulareingabe in dieser Tabelle gespeichert.  
  
### So erstellen Sie eine Suchtabelle  
  
1.  Fügen Sie dem Formular ein Steuerelement "<xref:System.Windows.Forms.ComboBox>", "<xref:System.Windows.Forms.ListBox>", oder "<xref:System.Windows.Forms.CheckedListBox>" hinzu.  
  
2.  Stellen Sie eine Verbindung zur Datenquelle her.  
  
3.  Richten Sie eine Datenbeziehung zwischen den beiden Tabellen ein.  Siehe [Einführung in DataRelation\-Objekte](../Topic/Introduction%20to%20DataRelation%20Objects.md).  
  
4.  Legen Sie die folgenden Eigenschaften fest.  Sie können im Code oder im Designer festgelegt werden.  
  
    |Eigenschaft|Einstellung|  
    |-----------------|-----------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|Die Tabelle, die Informationen darüber enthält, welche ID\-Nummer welchem Element entspricht.  Im vorherigen Szenario ist dies  `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|Die Spalte der Datenquellentabelle, die im Steuerelement angezeigt werden soll.  Im vorherigen Szenario handelt es sich hierbei um  `"Name"` . \(Verwenden Sie Anführungszeichen, um dies im Code festzulegen.\)|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|Die Spalte der Datenquellentabelle, die die gespeicherten Informationen enthält.  Im vorherigen Szenario handelt es sich hierbei um  `"ID"` . \(Verwenden Sie Anführungszeichen, um dies im Code festzulegen.\)|  
  
5.  Rufen Sie in einer Prozedur die Methode "<xref:System.Windows.Forms.ControlBindingsCollection.Add%2A>" der Klasse "<xref:System.Windows.Forms.ControlBindingsCollection>" auf, um die Eigenschaft "<xref:System.Windows.Forms.ListControl.SelectedValue%2A>" des Steuerelements an die Tabelle zu binden, die die Formulareingabe erfasst.  Sie können dies auch im Designer statt im Code tun, indem Sie im Fenster **Eigenschaften** auf die Eigenschaft "<xref:System.Windows.Forms.Control.DataBindings%2A>" des Steuerelements zugreifen.  Im vorherigen Szenario ist dies " `OrderDetailsTable`", und die Spalte ist  `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
  
    ```  
  
## Siehe auch  
 [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Übersicht über das ListBox\-Steuerelement](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Übersicht über das ComboBox\-Steuerelement](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Übersicht über das CheckedListBox\-Steuerelement](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)