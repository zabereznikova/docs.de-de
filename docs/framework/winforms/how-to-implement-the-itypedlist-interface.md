---
title: 'Vorgehensweise: Implementieren der ITypedList-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 2463a9c77a9836ff251e799056cc5131bf6c99e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084914"
---
# <a name="how-to-implement-the-itypedlist-interface"></a>Vorgehensweise: Implementieren der ITypedList-Schnittstelle
Implementieren der <xref:System.ComponentModel.ITypedList> Schnittstelle, um die Ermittlung des Schemas für eine bindbare Liste aktivieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Implementieren der <xref:System.ComponentModel.ITypedList> Schnittstelle. Ein generischer Typ mit dem Namen `SortableBindingList` leitet sich von der <xref:System.ComponentModel.BindingList%601> -Klasse und implementiert die <xref:System.ComponentModel.ITypedList> Schnittstelle. Eine einfache Klasse, die mit dem Namen `Customer` stellt Daten bereit, die für den Header des gebunden ist eine <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
