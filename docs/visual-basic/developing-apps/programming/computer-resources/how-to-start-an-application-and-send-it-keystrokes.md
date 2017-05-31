---
title: 'Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic) | Microsoft-Dokumentation'
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
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 314d62ae0699e63aab2dff25cce2ce37552e2a20
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Code: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)
In diesem Beispiel wird die `Shell`-Funktion verwendet, um die Anwendung „Rechner“ zu starten und anschließend werden zwei Zahlen multipliziert, indem Sie mithilfe der `My.Computer.Keyboard.SendKeys`-Methode Tastatureingaben senden.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Eine <xref:System.ArgumentException> -Ausnahme wird ausgegeben, wenn eine Anwendung mit dem angeforderten Prozessbezeichner nicht gefunden werden kann.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Der Aufruf der `Shell`-Funktion erfordert volles Vertrauen (<xref:System.Security.SecurityException>-Klasse).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
