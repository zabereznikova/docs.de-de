---
title: "Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten | Microsoft Docs"
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
  - "Gebundene Steuerelemente, Kombinationsfelder"
  - "Kombinationsfelder, Datenbindung"
  - "ComboBox-Steuerelement [Windows Forms], Datenbindung"
  - "Daten [Windows Forms], Binden an Steuerelemente"
  - "Datenbindung, Kombinationsfelder"
  - "Datengebundene Steuerelemente, Windows Forms"
  - "Listenfelder, Datenbindung"
  - "ListBox-Steuerelement [Windows Forms], Datenbindung"
  - "Windows Forms-Steuerelemente, Datenbindung"
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten
Sie können <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> an Daten binden, um folgende Aufgaben auszuführen: Durchsuchen von Daten in einer Datenbank, Eingeben neuer oder Bearbeiten vorhandener Daten.  
  
### So binden Sie ein Kombinationsfeld\- oder ListBox\-Steuerelement  
  
1.  Legen Sie die `DataSource` \-Eigenschaft auf ein Datenquellenobjekt fest.  Folgende Datenquellen sind zulässig: <xref:System.Windows.Forms.BindingSource> mit Datenbindung, Datentabellen, Datenansichten, DataSets, Datenansichten\-Manager, Arrays oder Klassen, die die <xref:System.Collections.IList>\-Schnittstelle implementieren.  Weitere Informationen finden Sie unter [Von Windows Forms unterstützte Datenquellen](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  Wenn Sie eine Bindung an eine Tabelle vornehmen, legen Sie die `DisplayMember` \-Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.  
  
     \- oder \-  
  
     Wenn Sie eine Bindung an <xref:System.Collections.IList> vornehmen, legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
  
    ```  
  
    > [!NOTE]
    >  Bei einer Bindung an eine Datenquelle, die nicht die <xref:System.ComponentModel.IBindingList>\-Schnittstelle implementiert, beispielsweise <xref:System.Collections.ArrayList>, werden die Daten des gebundenen Steuerelements nicht zusammen mit der Datenquelle aktualisiert.  Wenn beispielsweise ein Kombinationsfeld an <xref:System.Collections.ArrayList> gebunden ist und <xref:System.Collections.ArrayList> Daten hinzugefügt werden, werden diese neuen Elemente nicht im Kombinationsfeld angezeigt.  Sie können jedoch eine Aktualisierung des Kombinationsfeldes erzwingen, indem Sie die <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A>\-Methode und die <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A>\-Methode für die Instanz der <xref:System.Windows.Forms.BindingContext>\-Klasse aufrufen, an die das Steuerelement gebunden ist.  
  
## Siehe auch  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Datenbindung in Web Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Steuerelemente in Windows Forms zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)