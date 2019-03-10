---
title: 'Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 51c0b1fa535921b7b33a16f55bdc8b76d6125e72
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704088"
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
