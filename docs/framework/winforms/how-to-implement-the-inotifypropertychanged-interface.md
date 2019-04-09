---
title: 'Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: cfdfb22fd854a8f630243e0f612761c71cb778d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225598"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="5f72f-102">Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f72f-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="5f72f-103">Im folgenden Codebeispiel wird veranschaulicht, wie zum Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5f72f-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="5f72f-104">Implementieren Sie diese Schnittstelle für Business-Objekte, die in Windows Forms-Datenbindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f72f-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="5f72f-105">Bei der Implementierung, kommuniziert die Schnittstelle an ein gebundenes Steuerelement die eigenschaftenänderungen für ein Geschäftsobjekt.</span><span class="sxs-lookup"><span data-stu-id="5f72f-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f72f-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5f72f-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f72f-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f72f-107">See also</span></span>

- [<span data-ttu-id="5f72f-108">Vorgehensweise: Anwenden des PropertyNameChanged-Musters</span><span class="sxs-lookup"><span data-stu-id="5f72f-108">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)
- [<span data-ttu-id="5f72f-109">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="5f72f-109">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="5f72f-110">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe von BindingSource und der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f72f-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](./controls/raise-change-notifications--bindingsource.md)
- [<span data-ttu-id="5f72f-111">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="5f72f-111">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
