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
ms.openlocfilehash: f823d9e80eb644487eab1ed84345dd8bdc10efc2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64600943"
---
# <a name="value-types-and-reference-types"></a>Wert- und Verweistypen
In Visual Basic werden Datentypen basierend auf deren Klassifizierung implementiert. Die Visual Basic-Datentypen werden anhand des Verhaltens klassifiziert, je nachdem, ob eine Variable eines bestimmten Typs die eigenen Daten speichert oder einen Zeiger auf die Daten. Wenn sie ihre eigenen Daten speichert, handelt es sich um einen *Werttyp*. Wenn sie einen Zeiger auf die Daten an einer anderer Stelle im Arbeitsspeicher enthält, ist es eim *Verweistyp*.  
  
## <a name="value-types"></a>Werttypen  
 Ein Datentyp ist ein *Werttyp* , wenn er die Daten in einer eigenen Speicherbelegung enthält. Die folgenden sind Beispiele für Werttypen:  
  
- Alle numerischen Datentypen  
  
- `Boolean`, `Char`und `Date`  
  
- Alle Strukturen, auch wenn deren Member Verweistypen sind.  
  
- Enumerationen, da der zugrunde liegende Typ immer `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger` oder `ULong` ist  
  
 Jede Struktur ist ein Werttyp, auch wenn sie Verweistypmember enthält. Aus diesem Grund werden Werttypen wie z. B. `Char` und `Integer` von .NET Framework-Strukturen implementiert.  
  
 Sie können einen Werttyp deklarieren, indem Sie das reservierte Schlüsselwort verwenden, z. B. `Decimal`. Sie können auch das Schlüsselwort `New` verwenden, um einen Werttyp zu initialisieren. Dies ist besonders nützlich, wenn der Typ über einen Konstruktor verfügt, der Parameter annimmt. Ein Beispiel hierfür ist der Konstruktor <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>, der einen neue `Decimal`-Wert aus den angegebenen Teilen erstellt.  
  
## <a name="reference-types"></a>Verweistypen  
 Ein *Verweistyp* enthält einen Zeiger auf einen anderen Speicherort, das Daten enthält. Verweistypen umfassen Folgendes:  
  
- `String`  
  
- Alle Arrays, auch wenn ihre Elemente Werttypen sind.  
  
- Klassentypen Sie, z. B. <xref:System.Windows.Forms.Form>  
  
- Delegaten  
  
 Eine Klasse ist eine *Verweistyp*. Aus diesem Grund verweisen auf Typen wie z. B. `Object` und `String` werden von unterstützt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klassen. Beachten Sie, dass jedes Array ein Verweistyp ist, auch wenn seine Member Werttypen sind.  
  
 Da jede Verweistyp eine zugrunde liegende .NET Framework-Klasse darstellt, müssen Sie verwenden die [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md) Schlüsselwort, die Sie bei der Initialisierung. Die folgende Anweisung initialisiert ein Array.  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elemente, die keine Typen sind  
 Die folgenden Programmierelemente gelten nicht als Typen, da Sie keines davon als Datentyp für ein deklariertes Element angeben können:  
  
- Namespaces  
  
- Module  
  
- Ereignisse  
  
- Eigenschaften und Prozeduren  
  
- Variablen, Konstanten und Felder  
  
## <a name="working-with-the-object-data-type"></a>Arbeiten mit den Object-Datentyp  
 Sie können entweder ein Verweistyp oder ein Werttyp zuweisen, um eine Variable vom die `Object` -Datentyp. Ein `Object` -Variable enthält immer einen Zeiger auf die Daten nie die Daten selbst. Jedoch wenn Sie einen Werttyp zum Zuweisen einer `Object` Variablen, verhält es sich, als ob es sich um seine eigenen Daten enthält. Weitere Informationen finden Sie unter [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Finden Sie heraus, ob ein `Object` Variablen fungiert als ein Verweistyp oder ein Werttyp durch Übergabe an die <xref:Microsoft.VisualBasic.Information.IsReference%2A> -Methode in der die <xref:Microsoft.VisualBasic.Information> Klasse von der <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Gibt `True` Wenn den Inhalt der `Object` Variable stellt einen Verweistyp handelt.  
  
## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Typkonvertierung in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Effiziente Verwendung von Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
