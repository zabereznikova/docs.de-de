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
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604424"
---
# <a name="end-statement"></a>End Statement
Beendet die Ausführung sofort.  
  
## <a name="syntax"></a>Syntax  
  
```  
End  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzieren der `End` Anweisung an einer beliebigen Stelle in einer Prozedur, um die gesamte Anwendung zur Beendigung der Ausführung zu erzwingen. `End` Schließt alle geöffneten mit einer `Open` Anweisung und löscht alle für die Anwendung Variablen. Die Anwendung wird geschlossen, sobald keine andere Programme enthalten Verweise auf die Objekte vorhanden sind und kein Code ausgeführt wird.  
  
> [!NOTE]
>  Die `End` Anweisung abrupt beendet die Ausführung von Code und keine aufgerufen werden der `Dispose` oder `Finalize` -Methode oder andere Visual Basic-Code. Objektverweise, die von anderen Programmen werden ungültig. Wenn ein `End` -Anweisung innerhalb einer `Try` oder `Catch` Block Steuerelement übergibt keine entsprechenden `Finally` Block.  
  
 Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, schließen Sie alle Dateien oder keine Variablen löschen, es sei denn, sie in eine kompilierte ausführbare Datei (.exe) entdeckt wird.  
  
 Da `End` beendet die Anwendung ohne die Teilnahme an alle Ressourcen, die geöffnet werden können, sollten Sie versuchen, ordnungsgemäß beendet vor dem verwenden. Beispielsweise verfügt die Anwendung alle Formulare öffnen, schließen sie die bevor die Steuerung der `End` Anweisung.  
  
 Verwenden Sie `End` sparsam und nur, wenn Sie die Anwendung sofort beenden müssen. Die normalen Verfahren zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) nicht nur die Prozedur ordnungsgemäß beendet, sondern auch dem aufrufenden Code die Gelegenheit ordnungsgemäß zu beenden. Eine Konsolenanwendung kann z. B. einfach `Return` aus der `Main` Prozedur.  
  
> [!IMPORTANT]
>  Die `End` Anweisung ruft die <xref:System.Environment.Exit%2A> Methode der <xref:System.Environment> -Klasse in der <xref:System> Namespace. <xref:System.Environment.Exit%2A> benötigen Sie `UnmanagedCode` Berechtigung. Wenn Sie kein <xref:System.Security.SecurityException> Fehler auftritt.  
  
 Wenn ein zusätzlicher Schlüsselwort, gefolgt [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) kennzeichnet das Ende der Definition der entsprechenden Prozedur oder des Blocks. Beispielsweise `End Function` beendet die Definition einer `Function` Prozedur.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `End` Anweisung, um die Ausführung von Code zu beenden, wenn der Benutzer angefordert.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>Entwicklerhinweise für intelligente Geräte  
 Diese Anweisung wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
