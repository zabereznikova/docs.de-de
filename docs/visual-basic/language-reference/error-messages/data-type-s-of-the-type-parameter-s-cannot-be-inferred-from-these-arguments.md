---
title: Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
ms.openlocfilehash: 81535e3272eaed587288c26c4a4b9649467abed8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963564"
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a>Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden
Die Datentypen der Typparameter können nicht von diesen Argumenten abgeleitet werden. Sie können diesen Fehler möglicherweise beheben, indem Sie die Datentypen explizit angeben.  
  
 Dieser Fehler tritt auf, wenn die Überladungsauflösung fehlgeschlagen ist. Er wird als untergeordnete Meldung angezeigt, die den Grund für die Entfernung einer bestimmten Überladung angibt. In der Fehlermeldung wird erläutert, dass der Compiler den Typrückschluss nicht zum Suchen von Datentypen für die Typparameter verwenden kann.  
  
> [!NOTE]
> Wenn die Angabe von Argumenten keine Option ist (z. B. für Abfrageoperatoren in Abfrageausdrücken), wird nur der erste Satz der Fehlermeldung angezeigt.  
  
 Der folgende Code verdeutlicht den Fehler.  
  
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
  
- Anstelle des Typrückschlusses können Sie einen Datentyp für den oder die Typparameter angeben.  
  
## <a name="see-also"></a>Siehe auch

- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Typkonvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
