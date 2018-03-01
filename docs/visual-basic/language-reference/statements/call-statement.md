---
title: Call-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a>Call-Anweisung (Visual Basic)
Überträgt die Steuerung an eine `Function`, `Sub`, oder eine Dynamic Link Library (DLL)-Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Teile  
 `procedureName`  
 Erforderlich. Der Name der Prozedur aufrufen.  
  
 `argumentList`  
 Dies ist optional. Liste der Variablen oder Ausdrücke, die Argumente, die an die Prozedur übergeben werden, wenn sie aufgerufen wird, darstellt. Mehrere Argumente werden durch Kommas getrennt. Wenn Sie aufnehmen `argumentList`, müssen Sie es in Klammern einschließen.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Call` -Schlüsselwort, wenn Sie eine Prozedur aufrufen. Für die meisten Prozeduraufrufe müssen Sie keine dieses Schlüsselwort verwenden.  
  
 In der Regel die `Call` -Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einem Bezeichner gestartet. Verwenden der `Call` Schlüsselwort für andere Zwecke nicht empfohlen.  
  
 Wenn die Prozedur einen Wert zurückgibt, der `Call` Anweisung wird diese verworfen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt zwei Beispiele, in denen die `Call` Schlüsselwort ist erforderlich, um eine Prozedur aufrufen. In beiden Beispielen beginnt der aufgerufene Ausdruck mit einem Bezeichner nicht.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
