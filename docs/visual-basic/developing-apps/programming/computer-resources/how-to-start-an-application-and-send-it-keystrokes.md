---
title: 'Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben – Visual Basic'
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919390"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Vorgehensweise: Starten von Anwendungen und Senden von Tastatureingaben (Visual Basic)

In diesem Beispiel wird die <xref:Microsoft.VisualBasic.Interaction.Shell%2A>-Methode verwendet, um die Editor-Anwendung zu starten, und dann wird ein Satz gedruckt, indem mithilfe der [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A)-Methode Tastatureingaben gesendet werden.

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
