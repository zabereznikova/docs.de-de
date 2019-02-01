---
title: 'Vorgehensweise: Überprüfen des Verbindungsstatus in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: c7a43fd154616e516f8c5e7d36d25f34924649ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499959"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a>Vorgehensweise: Überprüfen des Verbindungsstatus in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>-Eigenschaft kann verwendet werden, um zu ermitteln, ob der Computer über eine funktionierende Netzwerk- oder Internetverbindung verfügt.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>So überprüfen Sie, ob ein Computer über eine funktionierende Verbindung verfügt  
  
-   Bestimmen Sie, ob die `IsAvailable`-Eigenschaft `True` oder `False` ist. Im folgende Code wird der Status der Eigenschaft überprüft und ausgegeben:  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
