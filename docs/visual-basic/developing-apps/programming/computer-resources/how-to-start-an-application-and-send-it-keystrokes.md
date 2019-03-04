---
title: 'Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: f130429e5b0964dc8680441fb83cb06d45904a69
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966202"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)
In diesem Beispiel wird die `Shell`-Funktion verwendet, um die Anwendung „Rechner“ zu starten und anschließend werden zwei Zahlen multipliziert, indem Sie mithilfe der `My.Computer.Keyboard.SendKeys`-Methode Tastatureingaben senden.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Eine <xref:System.ArgumentException>-Ausnahme wird ausgegeben, wenn eine Anwendung mit dem angeforderten Prozessbezeichner nicht gefunden werden kann.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Ein Aufruf der `Shell`-Funktion erfordert volles Vertrauen (<xref:System.Security.SecurityException>-Klasse).  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
