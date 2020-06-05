---
title: Wert- und Verweistypen
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 3a1de120f5f97ba93939f332f121d70cd3091216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392973"
---
# <a name="value-types-and-reference-types"></a>Wert- und Verweistypen
Es gibt zwei Arten von Typen in Visual Basic: Verweis Typen und Werttypen. Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten. Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird. Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und es ist nicht möglich, dass sich Vorgänge für eine Variable auf den anderen auswirken (außer im Fall des [ByRef-Modifizierers für Parameter](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Werttypen  
 Ein Datentyp ist ein *Werttyp* , wenn die Daten in der eigenen Speicher Belegung enthalten sind. Zu den Werttypen zählen die folgenden:  
  
- Alle numerischen Datentypen  
  
- `Boolean`, `Char` und `Date`  
  
- Alle Strukturen, auch wenn ihre Member Verweis Typen sind  
  
- Enumerationen, da der zugrunde liegende Typ immer `SByte` , `Short` , `Integer` , `Long` , `Byte` , `UShort` , `UInteger` oder ist.`ULong`  
  
 Jede Struktur ist ein Werttyp, auch wenn Sie Verweistyp Member enthält. Aus diesem Grund werden Werttypen wie `Char` und `Integer` durch .NET Framework Strukturen implementiert.  
  
 Sie können einen Werttyp deklarieren, indem Sie das reservierte Schlüsselwort verwenden, z `Decimal` . b.. Sie können auch das- `New` Schlüsselwort verwenden, um einen Werttyp zu initialisieren. Dies ist besonders nützlich, wenn der Typ über einen Konstruktor verfügt, der Parameter annimmt. Ein Beispiel hierfür ist der- <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> Konstruktor, der einen neuen `Decimal` Wert aus den angegebenen Teilen erstellt.  
  
## <a name="reference-types"></a>Verweistypen  
 Ein *Verweistyp* speichert einen Verweis auf seine Daten. Verweis Typen umfassen Folgendes:  
  
- `String`  
  
- Alle Arrays, auch wenn ihre Elemente Werttypen sind  
  
- Klassentypen, z. b.<xref:System.Windows.Forms.Form>  
  
- Delegaten  
  
 Eine Klasse ist ein *Verweistyp*. Beachten Sie, dass jedes Array ein Verweistyp ist, auch wenn seine Member Werttypen sind.  
  
 Da jeder Verweistyp eine zugrunde liegende .NET Framework Klasse darstellt, müssen Sie das [neue Operator](../../../language-reference/operators/new-operator.md) Schlüsselwort verwenden, wenn Sie es initialisieren. Mit der folgenden Anweisung wird ein Array initialisiert.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elemente, die keine Typen sind  
 Die folgenden Programmier Elemente sind nicht als-Typen qualifiziert, da Sie Sie nicht als Datentyp für ein deklariertes Element angeben können:  
  
- Namespaces  
  
- Module  
  
- Events  
  
- Eigenschaften und Prozeduren  
  
- Variablen, Konstanten und Felder  
  
## <a name="working-with-the-object-data-type"></a>Arbeiten mit dem Object-Datentyp  
 Sie können einer Variablen des-Datentyps entweder einen Verweistyp oder einen Werttyp zuweisen `Object` . Eine `Object` Variable enthält immer einen Verweis auf die Daten, nie die Daten selbst. Wenn Sie jedoch einer Variablen einen Werttyp zuweisen `Object` , verhält er sich so, als ob er seine eigenen Daten enthält. Weitere Informationen finden Sie unter [Object Data Type](../../../language-reference/data-types/object-data-type.md).  
  
 Sie können herausfinden, ob eine `Object` Variable als Verweistyp oder Werttyp fungiert, indem Sie Sie an die- <xref:Microsoft.VisualBasic.Information.IsReference%2A> Methode in der- <xref:Microsoft.VisualBasic.Information> Klasse des- <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace übergeben. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Gibt zurück, `True` Wenn der Inhalt der `Object` Variablen einen Verweistyp darstellt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Nullable-Werttypen](nullable-value-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Structure Statement](../../../language-reference/statements/structure-statement.md)
- [Effiziente Verwendung von Datentypen](efficient-use-of-data-types.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Datentypen](index.md)
