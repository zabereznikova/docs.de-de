---
title: 'Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen für Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: f1cc4a26929a39e85fa6028613b0712cc76ed4f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644230"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Vorgehensweise: Entfernen von Elementen aus DomainUpDown-Steuerelementen für Windows Forms
Entfernen von Elementen aus den Windows-Formularen <xref:System.Windows.Forms.DomainUpDown> Steuerelement durch Aufrufen der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse. Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> -Methode entfernt ein bestimmtes Element, während die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode entfernt ein Element anhand seiner Position.  
  
### <a name="to-remove-an-item"></a>So entfernen Sie ein Element  
  
-   Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse, um ein Element anhand des Namens zu entfernen.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     - oder -   
  
-   Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> Methode, um ein Element anhand seiner Position zu entfernen.  
  
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
- [DomainUpDown-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
- [Übersicht über das DomainUpDown-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
