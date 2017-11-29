---
title: 'Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6193e4cc86a470f046c220dc21150e0fc0bf792a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Gewusst wie: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten
Sie können Binden der <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> auf Daten zu Aufgaben wie das Durchsuchen von Daten in einer Datenbank, neue Daten eingeben oder Bearbeiten vorhandener Daten.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>So binden ein Kombinations- oder Listenfeld-Steuerelement  
  
1.  Legen Sie die `DataSource` -Eigenschaft auf ein Datenquellenobjekt. Mögliche Datenquellen umfassen eine <xref:System.Windows.Forms.BindingSource> an Daten, eine Datentabelle, eine Data source View, ein Dataset gebunden ist, eine Datenansicht-Manager, ein Array oder jede Klasse, implementiert die <xref:System.Collections.IList> Schnittstelle. Weitere Informationen finden Sie unter [von Windows Forms unterstützte Datenquellen](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  Wenn Sie in eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle.  
  
     \- oder –  
  
     Wenn Sie eine Bindung an eine <xref:System.Collections.IList>, legen Sie eine öffentliche Eigenschaft des Typs in der Liste der Anzeigemember.  
  
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
    >  Wenn Sie eine Datenquelle gebunden sind, die nicht implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle, wie ein <xref:System.Collections.ArrayList>, das gebundene Steuerelement Daten werden nicht aktualisiert werden, wenn die Datenquelle aktualisiert wird. Z. B. Wenn Sie über ein Kombinationsfeld gebunden zu einer <xref:System.Collections.ArrayList> und Daten hinzugefügt werden die <xref:System.Collections.ArrayList>, diese neuen Elemente nicht im Kombinationsfeld angezeigt. Allerdings können Sie erzwingen, das Kombinationsfeld aufrufen aktualisiert werden die <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> und <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methoden für die Instanz die <xref:System.Windows.Forms.BindingContext> Klasse, die das Steuerelement gebunden ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [Windows Forms-Datenbindung](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Datenbindung und Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows Forms-Steuerelemente zum Auflisten von Optionen](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
