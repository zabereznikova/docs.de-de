---
title: "Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b290c25286dce2236823919e8287db9abefc0dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden
Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden. Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.  
  
 Dieser Fehler tritt auf, wenn die Überladungsauflösung fehlgeschlagen ist. Er wird als untergeordnete Meldung angezeigt, die den Grund für die Entfernung einer bestimmten Überladung angibt. Die Fehlermeldung wird erläutert, dass der Compiler Typrückschluss verwenden kann, um die Datentypen der Typparameter suchen kann.  
  
> [!NOTE]
>  Wenn die Angabe von Argumenten keine Option ist (z. B. für Abfrageoperatoren in Abfrageausdrücken), wird nur der erste Satz der Fehlermeldung angezeigt.  
  
 Im folgenden Code wird der Fehler veranschaulicht.  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 **Fehler-ID:** BC36647 und BC36644  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Anstelle des Typrückschlusses können Sie einen Datentyp für den oder die Typparameter angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Generische Prozeduren in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [Konvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
