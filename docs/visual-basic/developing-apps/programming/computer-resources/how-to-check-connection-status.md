---
title: "Vorgehensweise: Überprüfen des Verbindungsstatus in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Web connections
- IsAvailable property, about IsAvailable
- connections, checking status
- connection status
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 81386ee1f8c8cefbcd34a05d594277b9de772b8d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a>Gewusst wie: Überprüfen des Verbindungsstatus in Visual Basic
Die <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>-Eigenschaft kann verwendet werden, um zu bestimmen, ob der Computer über ein funktionierendes Netzwerk oder Internetverbindung verfügt.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a>So überprüfen Sie, ob ein Computer über eine funktionierende Verbindung verfügt  
  
-   Bestimmen Sie, ob die `IsAvailable`-Eigenschaft `True` oder `False` ist. Im folgende Code wird der Status der Eigenschaft überprüft und ausgegeben:  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden. Weitere Informationen finden Sie unter [Codeausschnitte](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>

