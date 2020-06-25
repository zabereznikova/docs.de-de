---
title: ComboBox-Steuerelement oder ListBox-Steuerelement an Daten binden
description: Erfahren Sie, wie Sie die Windows Forms ComboBox und ListBox an Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.
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
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324065"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Vorgehensweise: Binden eines ComboBox-Steuerelements oder ListBox-Steuerelements in Windows Forms an Daten
Sie können <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> an Daten binden, um Aufgaben wie das Durchsuchen von Daten in einer Datenbank, das Eingeben neuer Daten oder das Bearbeiten vorhandener Daten auszuführen.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>So binden Sie ein ComboBox-oder ListBox-Steuerelement  
  
1. Legen Sie die- `DataSource` Eigenschaft auf ein Datenquellen Objekt fest. Mögliche Datenquellen sind eine <xref:System.Windows.Forms.BindingSource> gebundene Datenquelle, eine Datentabelle, eine Datenansicht, ein DataSet, ein Datenansichts-Manager, ein Array oder eine beliebige Klasse, die die <xref:System.Collections.IList> Schnittstelle implementiert. Weitere Informationen finden Sie [unter von Windows Forms unterstützte Datenquellen](../data-sources-supported-by-windows-forms.md).  
  
2. Wenn Sie an eine Tabelle binden, legen Sie die- `DisplayMember` Eigenschaft auf den Namen einer Spalte in der Datenquelle fest.  
  
     \- oder -  
  
     Wenn Sie an eine binden <xref:System.Collections.IList> , legen Sie den Anzeigemember auf eine öffentliche Eigenschaft des Typs in der Liste fest.  
  
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
    > Wenn Sie an eine Datenquelle gebunden sind, die die-Schnittstelle nicht implementiert (z. b.) <xref:System.ComponentModel.IBindingList> <xref:System.Collections.ArrayList> , werden die Daten des gebundenen Steuer Elements nicht aktualisiert, wenn die Datenquelle aktualisiert wird. Wenn Sie z. b. ein Kombinations Feld an ein-Element gebunden haben <xref:System.Collections.ArrayList> und Daten zu hinzugefügt <xref:System.Collections.ArrayList> werden, werden diese neuen Elemente nicht im Kombinations Feld angezeigt. Sie können jedoch erzwingen, dass das Kombinations Feld aktualisiert wird, indem Sie die <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> -Methode und die- <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> Methode für die Instanz der- <xref:System.Windows.Forms.BindingContext> Klasse aufrufen, an die das Steuerelement gebunden ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Datenbindung in Web Forms](../windows-forms-data-binding.md)
- [Datenbindung und Windows Forms](../data-binding-and-windows-forms.md)
- [Steuerelemente in Windows Forms zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
