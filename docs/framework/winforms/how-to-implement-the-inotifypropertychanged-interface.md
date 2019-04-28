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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802036"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle
Im folgenden Codebeispiel wird veranschaulicht, wie zum Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Implementieren Sie diese Schnittstelle für Business-Objekte, die in Windows Forms-Datenbindung verwendet werden. Bei der Implementierung, kommuniziert die Schnittstelle an ein gebundenes Steuerelement die eigenschaftenänderungen für ein Geschäftsobjekt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anwenden des PropertyNameChanged-Musters](how-to-apply-the-propertynamechanged-pattern.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
- [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle](./controls/raise-change-notifications--bindingsource.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
