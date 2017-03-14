---
title: "How to: Start an Application and Send it Keystrokes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "keystrokes, sending"
  - "Shell command example [Visual Basic]"
  - "processes, starting and sending keystrokes"
  - "SendKeys.SendWait examples"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Start an Application and Send it Keystrokes (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In diesem Beispiel wird die `Shell`\-Funktion verwendet, um die Rechneranwendung zu starten. Anschließend werden zwei Zahlen multipliziert, indem Tastatureingaben mithilfe der `My.Computer.Keyboard.SendKeys`\-Methode gesendet werden.  
  
## Beispiel  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## Robuste Programmierung  
 Eine <xref:System.ArgumentException>\-Ausnahme wird ausgelöst, wenn die Anwendung mit der angeforderten Prozess\-ID nicht gefunden werden kann.  
  
## .NET Framework-Sicherheit  
 Der Aufruf der `Shell`\-Funktion erfordert volle Vertrauenswürdigkeit \(<xref:System.Security.SecurityException>\-Klasse\).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>