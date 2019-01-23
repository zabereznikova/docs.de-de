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
ms.openlocfilehash: 82856405ab3c9581b398f358e5bf9ecf989ce193
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539765"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Vorgehensweise: Anwenden des PropertyNameChanged-Musters
Im folgenden Codebeispiel wird veranschaulicht, wie zum Anwenden der *PropertyName*Changed-Muster in ein benutzerdefiniertes Steuerelement. Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms Datenbindungs-Engine verwendet werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um das vorherige Codebeispiel zu kompilieren:  
  
-   Fügen Sie den Code in eine leere Codedatei ein. Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)
- [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
- [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
