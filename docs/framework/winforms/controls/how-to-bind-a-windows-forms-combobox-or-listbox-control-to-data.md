---
title: 'Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten'
ms.date: 03/30/2017
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
ms.openlocfilehash: f361526c44f8fbb9ab282fe15ae109b67e8f01dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922751"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten
Sie können und <xref:System.Windows.Forms.ListBox> an <xref:System.Windows.Forms.ComboBox> Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>So binden Sie ein ComboBox-oder ListBox-Steuerelement  
  
1. Legen Sie `DataSource` die-Eigenschaft auf ein Datenquellen Objekt fest. Mögliche Datenquellen sind eine <xref:System.Windows.Forms.BindingSource> gebundene Datenquelle, eine Datentabelle, eine Datenansicht, ein DataSet, ein Datenansichts-Manager, ein Array oder eine beliebige Klasse, <xref:System.Collections.IList> die die Schnittstelle implementiert. Weitere Informationen finden Sie [unter von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).  
  
2. Wenn Sie an eine Tabelle binden, legen Sie die `DisplayMember` -Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.  
  
     \- oder –  
  
     Wenn Sie an eine <xref:System.Collections.IList>binden, legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.  
  
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
    > Wenn Sie an eine Datenquelle gebunden sind, die die <xref:System.ComponentModel.IBindingList> -Schnittstelle nicht implementiert (z <xref:System.Collections.ArrayList>. b.), werden die Daten des gebundenen Steuer Elements nicht aktualisiert, wenn die Datenquelle aktualisiert wird. Wenn Sie z. b. ein Kombinations Feld an ein <xref:System.Collections.ArrayList> -Element gebunden haben und Daten <xref:System.Collections.ArrayList>zu hinzugefügt werden, werden diese neuen Elemente nicht im Kombinations Feld angezeigt. Sie können jedoch erzwingen, dass das Kombinations Feld aktualisiert wird, indem Sie <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> die <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> -Methode und die-Methode <xref:System.Windows.Forms.BindingContext> für die Instanz der-Klasse aufrufen, an die das Steuerelement gebunden ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Windows Forms-Datenbindung](../windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](../data-binding-and-windows-forms.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
