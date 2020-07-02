---
title: 'Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle'
description: Erfahren Sie, wie Sie die INotifyPropertyChanged-Schnittstelle für Geschäftsobjekte implementieren, die in Windows Forms Datenbindung verwendet werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 83d2ef32787d2dbcd877bc77dcede10111098f8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619267"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle
Im folgenden Codebeispiel wird veranschaulicht, wie die- <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle implementiert wird. Implementieren Sie diese Schnittstelle für Geschäftsobjekte, die in Windows Forms Datenbindung verwendet werden. Wenn die-Schnittstelle implementiert ist, kommuniziert Sie mit einem gebundenen Steuerelement mit den Eigenschafts Änderungen für ein Geschäftsobjekt.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Anwenden des PropertyNameChanged-Musters](how-to-apply-the-propertynamechanged-pattern.md)
- [Datenbindung in Web Forms](windows-forms-data-binding.md)
- [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe von BindingSource und der INotifyPropertyChanged-Schnittstelle](./controls/raise-change-notifications--bindingsource.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
