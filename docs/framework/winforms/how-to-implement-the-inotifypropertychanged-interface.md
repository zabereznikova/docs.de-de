---
title: 'Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: c92406899cffa56a1001f50f89cb53303df5da39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560073"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle
Im folgenden Codebeispiel wird veranschaulicht, wie zum Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Implementieren Sie diese Schnittstelle für Business-Objekte, die in Windows Forms-Datenbindung verwendet werden. Bei der Implementierung, kommuniziert die Schnittstelle an ein gebundenes Steuerelement die eigenschaftenänderungen für ein Geschäftsobjekt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Anwenden des PropertyNameChanged-Musters](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)
- [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
