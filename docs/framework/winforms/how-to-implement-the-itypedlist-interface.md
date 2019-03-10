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
ms.openlocfilehash: df4b009ca225b4bf4290398ccd7dd252c9189915
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709790"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="89b2d-102">Vorgehensweise: Implementieren der ITypedList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89b2d-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="89b2d-103">Implementieren der <xref:System.ComponentModel.ITypedList> Schnittstelle, um die Ermittlung des Schemas für eine bindbare Liste aktivieren.</span><span class="sxs-lookup"><span data-stu-id="89b2d-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b2d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89b2d-104">Example</span></span>  
 <span data-ttu-id="89b2d-105">Im folgenden Codebeispiel wird veranschaulicht, wie zum Implementieren der <xref:System.ComponentModel.ITypedList> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="89b2d-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="89b2d-106">Ein generischer Typ mit dem Namen `SortableBindingList` leitet sich von der <xref:System.ComponentModel.BindingList%601> -Klasse und implementiert die <xref:System.ComponentModel.ITypedList> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="89b2d-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="89b2d-107">Eine einfache Klasse, die mit dem Namen `Customer` stellt Daten bereit, die für den Header des gebunden ist eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="89b2d-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89b2d-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="89b2d-108">Compiling the Code</span></span>  
 <span data-ttu-id="89b2d-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="89b2d-109">This example requires:</span></span>  
  
-   <span data-ttu-id="89b2d-110">Verweise auf die Assemblys ""System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="89b2d-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b2d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89b2d-111">See also</span></span>
- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="89b2d-112">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89b2d-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
