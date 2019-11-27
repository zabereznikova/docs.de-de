---
title: End Statement
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343725"
---
# <a name="end-statement"></a>End Statement
Beendet die Ausführung sofort.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `End`-Anweisung an beliebiger Stelle in einer Prozedur platzieren, um die Ausführung der gesamten Anwendung zu erzwingen. `End` schließt alle Dateien, die mit einer `Open`-Anweisung geöffnet wurden, und löscht alle Variablen der Anwendung. Die Anwendung wird geschlossen, sobald keine anderen Programme Verweise auf Ihre Objekte enthalten und der zugehörige Code nicht mehr ausgeführt wird.  
  
> [!NOTE]
> Die `End`-Anweisung beendet die Codeausführung abrupt und ruft nicht die `Dispose`-oder `Finalize`-Methode oder einen anderen Visual Basic Code auf. Objekt Verweise, die von anderen Programmen gehalten werden, werden für ungültig erklärt. Wenn eine `End`-Anweisung in einem `Try`-oder `Catch`-Block gefunden wird, wird die Steuerung nicht an den entsprechenden `Finally` Block übergeben.  
  
 Die `Stop`-Anweisung hält die Ausführung an, aber im Gegensatz zu `End`schließt Sie keine Dateien oder löscht Variablen, sofern Sie nicht in einer kompilierten ausführbaren Datei (. exe) gefunden wird.  
  
 Da `End` Ihre Anwendung beendet, ohne sich an Ressourcen zu wenden, die möglicherweise geöffnet sind, sollten Sie versuchen, die Anwendung ordnungsgemäß zu schließen, bevor Sie Sie verwenden. Wenn für Ihre Anwendung z. b. Formulare geöffnet sind, sollten Sie diese schließen, bevor die Steuerung die `End` Anweisung erreicht.  
  
 Sie sollten `End` sparsam und nur dann verwenden, wenn Sie sofort beenden müssen. Die normalen Methoden zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) schließen die Prozedur nicht nur ordnungsgemäß, sondern geben dem aufrufenden Code auch die Möglichkeit, sauber zu schließen. Eine Konsolenanwendung kann z. b. einfach aus dem `Main` Verfahren `Return`.  
  
> [!IMPORTANT]
> Die `End`-Anweisung ruft die <xref:System.Environment.Exit%2A>-Methode der <xref:System.Environment>-Klasse im <xref:System>-Namespace auf. <xref:System.Environment.Exit%2A> erfordert, dass Sie über `UnmanagedCode` Berechtigung verfügen. Wenn dies nicht der Fall ist, tritt ein <xref:System.Security.SecurityException> Fehler auf.  
  
 Wenn ein zusätzliches Schlüsselwort folgt, wird das Ende der Definition der entsprechenden Prozedur bzw. des entsprechenden Blocks durch die [End \<-Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) angegeben. Beispielsweise beendet `End Function` die Definition einer `Function` Prozedur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Codeausführung mithilfe der `End`-Anweisung beendet, wenn der Benutzer sie anfordert.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  
 Diese Anweisung wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<-Schlüsselwort > Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
