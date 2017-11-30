---
title: Throw-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Throw
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a>Throw-Anweisung (Visual Basic)
Löst eine Ausnahme innerhalb einer Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Enthält Informationen über die Ausnahme ausgelöst wird. Optional, wenn im wohnen eine `Catch` -Anweisung, ansonsten erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Die `Throw` -Anweisung löst eine Ausnahme, die Sie, mit dem Code für die strukturierte Ausnahmebehandlung behandeln können (`Try`... `Catch`... `Finally`) oder Code für die unstrukturierte Ausnahmebehandlung (`On Error GoTo`). Sie können die `Throw` Anweisung, um Fehler im Code abfangen, da Visual Basic der Aufrufliste verschoben, bis die entsprechenden Ausnahmebehandlungscode gefunden wird.  
  
 Ein `Throw` Anweisung ohne Ausdruck kann nur verwendet werden, einem `Catch` -Anweisung, in dem Fall die Anweisung die Ausnahme, die gerade verarbeitet wird löst, indem Sie die `Catch` Anweisung.  
  
 Die `Throw` Anweisung setzt die Aufrufliste für die `expression` Ausnahme. Wenn `expression` nicht angegeben wird, die Aufrufliste unverändert. Sie erreichen die Aufrufliste für die Ausnahme über die <xref:System.Exception.StackTrace%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Der folgende code verwendet die `Throw` Anweisung eine Ausnahme ausgelöst:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>Anforderungen  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Modul:**`Interaction`  
  
 **Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")  
  
## <a name="see-also"></a>Siehe auch  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
