---
title: 'Vorgehensweise: Anwenden des PropertyNameChanged-Musters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665260"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Vorgehensweise: Anwenden des PropertyNameChanged-Musters
Im folgenden Codebeispiel wird veranschaulicht, wie zum Anwenden der *PropertyName*Changed-Muster in ein benutzerdefiniertes Steuerelement. Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms Datenbindungs-Engine verwendet werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um das vorherige Codebeispiel zu kompilieren:  
  
- Fügen Sie den Code in eine leere Codedatei ein. Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle](how-to-implement-the-inotifypropertychanged-interface.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](change-notification-in-windows-forms-data-binding.md)
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
