---
title: Throw-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 9af1436af950346eef572c34b9d42da3e8c8cf24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671160"
---
# <a name="throw-statement-visual-basic"></a>Throw-Anweisung (Visual Basic)
Löst eine Ausnahme in einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Enthält Informationen über die Ausnahme ausgelöst wird. Optional, wenn im wohnen eine `Catch` -Anweisung, andernfalls erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Die `Throw` -Anweisung löst eine Ausnahme, die Sie mit Code für die strukturierte Ausnahmebehandlung (`Try`... `Catch`... `Finally`) oder Code für die unstrukturierte Ausnahmebehandlung (`On Error GoTo`). Sie können die `Throw` Anweisung, um Fehler in Ihrem Code abfangen, da es sich bei Visual Basic die Aufrufliste nach oben verschoben, bis den entsprechenden Code für die Behandlung von Ausnahmen gefunden.  
  
 Ein `Throw` -Anweisung keinen Ausdruck kann nur verwendet werden, einem `Catch` -Anweisung, in dem Fall die Anweisung die Ausnahme, die gerade verarbeitet wird, indem Sie erneut die `Catch` Anweisung.  
  
 Die `Throw` Anweisung setzt die Aufrufliste für den `expression` Ausnahme. Wenn `expression` nicht angegeben wird, die Aufrufliste unverändert. Sie erreichen die Aufrufliste für die Ausnahme über die <xref:System.Exception.StackTrace%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Der folgende code verwendet die `Throw` Anweisung eine Ausnahme ausgelöst:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:** `Interaction`  
  
 **Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Siehe auch
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
