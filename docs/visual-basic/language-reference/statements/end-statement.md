---
title: End-Anweisung (Visual Basic)
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
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944469"
---
# <a name="end-statement"></a>End Statement
Beendet die Ausführung sofort.  
  
## <a name="syntax"></a>Syntax  
  
```  
End  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `End` -Anweisung an einer beliebigen Stelle in einer Prozedur platzieren, um die Ausführung der gesamten Anwendung zu erzwingen. `End`schließt alle Dateien, die mit `Open` einer-Anweisung geöffnet wurden, und löscht alle Variablen der Anwendung. Die Anwendung wird geschlossen, sobald keine anderen Programme Verweise auf Ihre Objekte enthalten und der zugehörige Code nicht mehr ausgeführt wird.  
  
> [!NOTE]
> Die `End` -Anweisung beendet die Codeausführung abrupt und ruft weder die `Dispose` - `Finalize` Methode noch die-Methode oder andere Visual Basic Code auf. Objekt Verweise, die von anderen Programmen gehalten werden, werden für ungültig erklärt. Wenn eine `End` -Anweisung in einem `Try` -oder `Catch` -Block gefunden wird, wird das-Steuer `Finally` Element nicht an den entsprechenden-Block übergeben.  
  
 Die `Stop` -Anweisung hält die Ausführung an, `End`aber im Gegensatz dazu schließt Sie keine Dateien oder löscht Variablen, es sei denn, Sie findet in einer kompilierten ausführbaren Datei (. exe).  
  
 Da `End` Ihre Anwendung beendet, ohne dass Sie an Ressourcen teilnimmt, die möglicherweise geöffnet sind, sollten Sie versuchen, die Anwendung ordnungsgemäß zu schließen, bevor Sie Sie verwenden. Wenn für Ihre Anwendung z. b. Formulare geöffnet sind, sollten Sie diese schließen, bevor die `End` Steuerung die-Anweisung erreicht.  
  
 Sie sollten nur `End` sparsam und nur dann verwenden, wenn Sie sofort beenden müssen. Die normalen Methoden zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) schließen die Prozedur nicht nur ordnungsgemäß, sondern geben dem aufrufenden Code auch die Möglichkeit, sauber zu schließen. Eine Konsolenanwendung kann z. b. einfach `Return` aus der `Main` Prozedur entfernt werden.  
  
> [!IMPORTANT]
> Die `End` -Anweisung ruft <xref:System.Environment.Exit%2A> die-Methode <xref:System.Environment> <xref:System> der-Klasse im-Namespace auf. <xref:System.Environment.Exit%2A>erfordert, dass Sie `UnmanagedCode` über die-Berechtigung verfügen. Andernfalls tritt ein <xref:System.Security.SecurityException> Fehler auf.  
  
 Wenn ein zusätzliches Schlüsselwort folgt, [wird \<das End-Schlüsselwort > Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) das Ende der Definition der entsprechenden Prozedur bzw. des entsprechenden Blocks verstreicht. `End Function` Beendet beispielsweise die Definition einer `Function` Prozedur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `End` -Anweisung verwendet, um die Codeausführung zu beenden, wenn der Benutzer sie anfordert.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  
 Diese Anweisung wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<-Schlüsselwort > Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
