---
title: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745580"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Gewusst wie: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen in Windows Forms
Sie können der Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement im Code Elemente hinzufügen. Ruft die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse auf, um der <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft des Steuer Elements Elemente hinzuzufügen. Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-Methode fügt ein Element am Ende einer Auflistung hinzu, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode ein Element an einer angegebenen Position hinzufügt.  
  
### <a name="to-add-a-new-item"></a>So fügen Sie ein neues Element hinzu  
  
1. Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>-Methode, um am Ende der Liste der Elemente ein Element hinzuzufügen.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     Oder  
  
2. Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A>-Methode, um ein Element an einer bestimmten Position in die Liste einzufügen.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown-Steuerelement](domainupdown-control-windows-forms.md)
- [Übersicht über das DomainUpDown-Steuerelement](domainupdown-control-overview-windows-forms.md)
