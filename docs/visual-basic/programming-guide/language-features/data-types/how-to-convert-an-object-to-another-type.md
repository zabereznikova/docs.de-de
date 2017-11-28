---
title: 'Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 053c93e7cf842138f5b9299cd2fcfa56342dd40b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic
Konvertieren Sie eine `Object` Variable in einen anderen Datentyp mithilfe einer wie [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein `Object` -Variable auf einen `Integer` und ein `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Wenn Sie wissen, dass der Inhalt des ein `Object` -Variablen eines bestimmten Datentyps, es ist besser, die Variable in diesen Datentyp zu konvertieren. Wenn Sie weiterhin verwenden die `Object` Variable anfallen entweder *Boxing* und *unboxing* (für einen Werttyp) oder *späte Bindung* (für einen Referenztyp darstellt). Diese Vorgänge alle zusätzlichen Ausführung Zeit in Anspruch nehmen, und stellen die Leistung langsamer.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Object>  
 [Konvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
