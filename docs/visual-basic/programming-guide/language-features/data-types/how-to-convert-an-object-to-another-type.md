---
title: 'Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: d80dc542f71aaf3eec6891006d77c5d39c985abf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64600996"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic
Konvertieren Sie eine `Object` Variable in einen anderen Datentyp mithilfe einer wie [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein `Object` Variable eine `Integer` und `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Wenn Sie wissen, dass der Inhalt des ein `Object` Variablen sind eines bestimmten Datentyps, es ist besser, die die Variable in diesen Datentyp zu konvertieren. Wenn Sie weiterhin die `Object` Variablen, es fallen entweder *Boxing* und *unboxing* (für einen Werttyp) oder *späte Bindung* (für einen Verweistyp). Diese Vorgänge alle zusätzlichen Ausführung Zeit in Anspruch nehmen, und stellen die Leistung langsamer.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Object>
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
