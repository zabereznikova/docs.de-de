---
title: 'Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: cdb78bc66867ce27076d7b7e42de6a2880cb3a8c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393960"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic
Sie konvertieren eine `Object` Variable in einen anderen Datentyp, indem Sie ein Konvertierungs Schlüsselwort wie die [CType-Funktion](../../../language-reference/functions/ctype-function.md)verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Object` -Variable in eine `Integer` und eine konvertiert `String` .  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Wenn Sie wissen, dass der Inhalt einer `Object` Variablen einen bestimmten Datentyp hat, ist es besser, die Variable in diesen Datentyp zu konvertieren. Wenn Sie die Variable weiterhin verwenden `Object` , werden entweder *Boxing* und *Unboxing* (bei einem Werttyp) oder eine *späte Bindung* (für einen Verweistyp) verursacht. Diese Vorgänge erfordern eine zusätzliche Ausführungszeit und machen die Leistung langsamer.  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Object>
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](conversions-between-strings-and-other-types.md)
- [Arraykonvertierungen](array-conversions.md)
- [Strukturen](structures.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
