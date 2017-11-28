---
title: 'Gewusst wie: Anwenden des PropertyNameChanged-Musters'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f53dd2fdaa622e022f49c153b6dbc83030ae791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Gewusst wie: Anwenden des PropertyNameChanged-Musters
Das folgende Codebeispiel veranschaulicht das Anwenden der *PropertyName*-Muster auf ein benutzerdefiniertes Steuerelement. Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms-Datenbindungsmodul verwendet werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 So kompilieren Sie das vorherige Codebeispiel:  
  
-   Fügen Sie den Code in eine leere Codedatei ein. Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Implementieren der INotifyPropertyChanged-Schnittstelle](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [Änderungsbenachrichtigung in der Windows Forms-Datenbindung](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Windows Forms-Datenbindung](../../../docs/framework/winforms/windows-forms-data-binding.md)
