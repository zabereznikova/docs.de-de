---
title: Entfernen von Elementen aus DomainUpDown-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735769"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Gewusst wie: Entfernen von Elementen aus DomainUpDown-Steuerelementen in Windows Forms
Sie können Elemente aus der Windows Forms <xref:System.Windows.Forms.DomainUpDown>-Steuerelement entfernen, indem Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse aufrufen. Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-Methode entfernt ein bestimmtes Element, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode ein Element nach seiner Position entfernt.  
  
### <a name="to-remove-an-item"></a>So entfernen Sie ein Element  
  
- Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>-Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>-Klasse, um ein Element anhand des Namens zu entfernen.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     \- oder -  
  
- Verwenden Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A>-Methode, um ein Element nach seiner Position zu entfernen.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown-Steuerelement](domainupdown-control-windows-forms.md)
- [Übersicht über das DomainUpDown-Steuerelement](domainupdown-control-overview-windows-forms.md)
