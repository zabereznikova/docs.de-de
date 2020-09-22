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
ms.openlocfilehash: 0c99b919b50701e93fab7caf5fb5d8b6b976d44b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865858"
---
# <a name="end-statement"></a>End Statement

Beendet die Ausführung sofort.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
End  
```  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können die- `End` Anweisung an einer beliebigen Stelle in einer Prozedur platzieren, um die Ausführung der gesamten Anwendung zu erzwingen. `End` schließt alle Dateien, die mit einer-Anweisung geöffnet wurden, `Open` und löscht alle Variablen der Anwendung. Die Anwendung wird geschlossen, sobald keine anderen Programme Verweise auf Ihre Objekte enthalten und der zugehörige Code nicht mehr ausgeführt wird.  
  
> [!NOTE]
> Die `End` -Anweisung beendet die Codeausführung abrupt und ruft weder die- `Dispose` Methode noch die- `Finalize` Methode oder andere Visual Basic Code auf. Objekt Verweise, die von anderen Programmen gehalten werden, werden für ungültig erklärt. Wenn eine- `End` Anweisung in einem- `Try` oder-Block gefunden wird, wird das-Steuerelement `Catch` nicht an den entsprechenden- `Finally` Block übergeben.  
  
 Die- `Stop` Anweisung hält die Ausführung an, aber im Gegensatz dazu `End` schließt Sie keine Dateien oder löscht Variablen, es sei denn, Sie findet in einer kompilierten ausführbaren Datei (. exe).  
  
 Da `End` Ihre Anwendung beendet, ohne dass Sie an Ressourcen teilnimmt, die möglicherweise geöffnet sind, sollten Sie versuchen, die Anwendung ordnungsgemäß zu schließen, bevor Sie Sie verwenden. Wenn für Ihre Anwendung z. b. Formulare geöffnet sind, sollten Sie diese schließen, bevor die Steuerung die- `End` Anweisung erreicht.  
  
 Sie sollten `End` nur sparsam und nur dann verwenden, wenn Sie sofort beenden müssen. Die normalen Methoden zum Beenden einer Prozedur ([Return-Anweisung](return-statement.md) und [Exit-Anweisung](exit-statement.md)) schließen die Prozedur nicht nur ordnungsgemäß, sondern geben dem aufrufenden Code auch die Möglichkeit, sauber zu schließen. Eine Konsolenanwendung kann z. b. einfach `Return` aus der `Main` Prozedur entfernt werden.  
  
> [!IMPORTANT]
> Die- `End` Anweisung ruft die- <xref:System.Environment.Exit%2A> Methode der- <xref:System.Environment> Klasse im- <xref:System> Namespace auf. <xref:System.Environment.Exit%2A> erfordert, dass Sie über die- `UnmanagedCode` Berechtigung verfügen. Andernfalls <xref:System.Security.SecurityException> tritt ein Fehler auf.  
  
 Wenn ein zusätzliches Schlüsselwort folgt, wird die [End- \<keyword> Anweisung](end-keyword-statement.md) das Ende der Definition der entsprechenden Prozedur bzw. des entsprechenden Blocks beschreiben. Beendet beispielsweise `End Function` die Definition einer `Function` Prozedur.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die- `End` Anweisung verwendet, um die Codeausführung zu beenden, wenn der Benutzer sie anfordert.  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>Entwickler Hinweise zu intelligenten Geräten  

 Diese Anweisung wird nicht unterstützt.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop-Anweisung](stop-statement.md)
- [End- \<keyword> Anweisung](end-keyword-statement.md)
