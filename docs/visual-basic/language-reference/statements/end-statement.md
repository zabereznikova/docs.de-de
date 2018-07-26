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
ms.openlocfilehash: 8fd489dc9f12f7e80ef2dd49c6e2dee6c28ae761
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199396"
---
# <a name="end-statement"></a>End Statement
Beendet die Ausführung sofort.  
  
## <a name="syntax"></a>Syntax  
  
```  
End  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzieren der `End` Anweisung an einer beliebigen Stelle in einer Prozedur zu erzwingen, dass die gesamte Anwendung nicht mehr ausgeführt wird. `End` Schließt alle geöffneten mit einer `Open` Anweisung und löscht alle für die Anwendung Variablen. Die Anwendung geschlossen wird, sobald es sind keine anderen Programme, die Verweise auf die Objekte enthält und kein Code ausgeführt wird.  
  
> [!NOTE]
>  Die `End` Anweisung abrupt beendet die Ausführung von Code und wird nicht aufgerufen werden. die `Dispose` oder `Finalize` Methode oder eine beliebige andere Visual Basic-Code. Objektverweise, die von anderen Programmen werden ungültig. Wenn ein `End` -Anweisung innerhalb einer `Try` oder `Catch` Block Steuerelement übergibt die nicht mit der entsprechenden `Finally` Block.  
  
 Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, keine Dateien schließen oder löschen Sie alle Variablen, es sei denn, es in eine kompilierte ausführbare Datei (.exe)-Datei gefunden wird.  
  
 Da `End` beendet die Anwendung ohne die Teilnahme an Ressourcen, die geöffnet sein können, sollten Sie versuchen, die ordnungsgemäß schließen vor der Verwendung. Beispielsweise verfügt die Anwendung aller Formulare zu öffnen, schließen sie die bevor die Steuerung der `End` Anweisung.  
  
 Verwenden Sie `End` sparsam und nur, wenn Sie die Anwendung sofort beenden müssen. Die normalen Verfahren zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) nicht nur das Verfahren ordnungsgemäß beendet, sondern auch dem aufrufenden Code die Möglichkeit, ordnungsgemäß zu beenden. Eine Konsolenanwendung kann z.B. einfach `Return` aus der `Main` Verfahren.  
  
> [!IMPORTANT]
>  Die `End` Anweisung ruft die <xref:System.Environment.Exit%2A> Methode der <xref:System.Environment> -Klasse in der <xref:System> Namespace. <xref:System.Environment.Exit%2A> benötigen Sie `UnmanagedCode` Berechtigung. Wenn Sie nicht, führen eine <xref:System.Security.SecurityException> Fehler auftritt.  
  
 Wenn ein zusätzliches Schlüsselwort gefolgt [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) kennzeichnet das Ende der Definition der entsprechenden Prozedur oder des Block. Z. B. `End Function` beendet die Definition einer `Function` Verfahren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `End` Anweisung, um die Ausführung von Code zu beenden, wenn der Benutzer es anfordert.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>Hinweise für Entwickler intelligente Geräte  
 Diese Anweisung wird nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Stop-Anweisung](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
