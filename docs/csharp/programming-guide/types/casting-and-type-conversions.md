---
title: Umwandlung und Typkonvertierungen – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: 252d509617ab5dbc53b282bac52e356396d82fab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711895"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)

Weil C# zur Kompilierzeit statisch typisiert ist, kann eine Variable, nachdem sie deklariert wurde, nicht erneut deklariert werden oder einen Wert von einem anderen Typ zugewiesen bekommen, es sei denn, dieser Typ ist implizit in den Typ der Variable konvertierbar. `string` kann beispielsweise nicht implizit in `int` konvertiert werden. Deshalb können Sie, nachdem Sie `i` als `int` deklariert haben, nicht die Zeichenfolge „Hello“ zuweisen. Dies wird im folgenden Beispiel veranschaulicht:
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 Manchmal müssen Sie möglicherweise einen Wert in eine Variable oder einen Methodenparameter eines anderen Typen kopieren. Sie haben z.B. möglicherweise eine Ganzzahlvariable, die Sie an eine Methode übergeben müssen, deren Parameter vom Type `double` ist. Möglicherweise müssen Sie auch einer Variablen eines Schnittstellentyps eine Klassenvariable zuweisen. Derartige Vorgänge werden als *Typkonvertierungen* bezeichnet. In C# können Sie folgende Arten von Konvertierungen durchführen:  
  
- **Implizite Konvertierungen**: Es ist keine besondere Syntax erforderlich, da die Konvertierung typsicher ist und keine Daten verloren gehen. Beispiele sind Konvertierungen von kleinere in größere Ganzzahltypen und Konvertierungen von abgeleiteten in Basisklassen.  
  
- **Explizite Konvertierungen (Umwandlungen)** : Für explizite Konvertierungen ist ein [Umwandlungsoperator`()`](../../language-reference/operators/type-testing-and-cast.md#cast-operator-) erforderlich. Eine Umwandlung ist erforderlich, wenn Informationen bei einer Konvertierung verloren gehen können oder wenn die Konvertierung aus anderen Gründen fehlschlagen könnte. Häufig auftretende Beispiele sind u.a. numerische Konvertierungen in einen Typen, der eine geringere Genauigkeit oder einen kleineren Bereich aufweist, oder Konvertierungen einer Instanz einer Basisklasse in eine abgeleitete Klasse.  
  
- **Benutzerdefinierte Konvertierungen**: Benutzerdefinierte Konvertierungen werden anhand spezieller Methoden durchgeführt, die Sie definieren können, um explizite und implizite Konvertierungen zwischen benutzerdefinierten Typen zu ermöglichen, die nicht in einer Beziehung „Basisklasse – abgeleitete Klasse“ zueinander stehen. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungsoperatoren](../../language-reference/operators/user-defined-conversion-operators.md).  
  
- **Konvertierungen mit Hilfsklassen**: Für eine Konvertierung von nicht kompatiblen Typen, z.B. von ganzen Zahlen und <xref:System.DateTime?displayProperty=nameWithType>-Objekten, oder von Hexadezimalzeichenfolgen und Bytearrays können Sie die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse, die <xref:System.Convert?displayProperty=nameWithType>-Klasse und die `Parse`-Methoden der integrierten numerischen Typen (z.B. <xref:System.Int32.Parse%2A?displayProperty=nameWithType>) verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ](./how-to-convert-a-byte-array-to-an-int.md), [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](./how-to-convert-a-string-to-a-number.md) und [Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
  
## <a name="implicit-conversions"></a>Implizite Konvertierungen

 Eine implizite Konvertierung kann für integrierte numerische Typen durchgeführt werden, wenn der zu speichernde Wert in die Variable passt, ohne abgeschnitten oder abgerundet zu werden. Für integrale Typen bedeutet dies, dass der Bereich des Quelltyps eine korrekte Teilmenge des Bereichs für den Zieltyp ist. Zum Beispiel kann eine Variable vom Typ [long](../../language-reference/builtin-types/integral-numeric-types.md) (64-Bit-Integer) jeden Wert speichern, den eine Variable vom Typ [int](../../language-reference/builtin-types/integral-numeric-types.md) (32-Bit-Integer) speichern kann. Im folgenden Beispiel konvertiert der Compiler den Wert von `num` auf der rechten Seite implizit in einen `long`-Typ, bevor er ihn `bigNum` zuweist.  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 Eine vollständige Liste aller impliziten numerischen Konvertierungen finden Sie unter [Implicit numeric conversions](../../language-reference/builtin-types/numeric-conversions.md#implicit-numeric-conversions) (Implizite numerische Konvertierungen) im Artikel [Built-in numeric conversions](../../language-reference/builtin-types/numeric-conversions.md) (Integrierte numerische Konvertierungen).
  
 Eine implizite Konvertierungen für Verweistypen von einer Klasse in jede ihrer direkten oder indirekten Basisklassen oder Schnittstellen ist immer möglich. Es ist keine spezielle Syntax erforderlich, da eine abgeleitete Klasse immer alle Member der Basisklasse enthält.  
  
```csharp
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Explizite Konvertierungen

 Wenn allerdings eine Konvertierung nicht ohne möglichen Informationsverlust durchgeführt werden kann, fordert der Compiler eine explizite Konvertierung; diese wird als *Umwandlung* bezeichnet. Eine Umwandlung bietet die Möglichkeit, den Compiler explizit zu verständigen, dass Sie eine Konvertierung vornehmen möchten, und dass es Ihnen bewusst ist, dass dies einen Datenverlust zur Folge haben kann. Wenn Sie eine Umwandlung durchführen möchten, geben Sie den Typ, in den umgewandelt werden soll, in Klammern am Anfang des zu konvertierenden Wertes oder der zu konvertierenden Variablen an. Das folgende Programm wandelt ein [double](../../language-reference/builtin-types/floating-point-numeric-types.md) in ein [int](../../language-reference/builtin-types/integral-numeric-types.md) um. Das Programm führt ohne die Umwandlung keine Kompilierung durch.  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 Eine vollständige Liste der expliziten numerischen Konvertierungen finden Sie unter [Explicit numeric conversions](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) (Explizite numerische Konvertierungen) im Artikel [Built-in numeric conversions](../../language-reference/builtin-types/numeric-conversions.md) (Integrierte numerische Konvertierungen).
  
 Eine explizite Umwandlung ist für Verweistypen erforderlich, wenn Sie von einer Basisklasse in eine abgeleitete Klasse konvertieren möchten:  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Ein Umwandlungsvorgang zwischen Verweistypen ändert nicht den Laufzeittypen des zugrunde liegenden Objekts; er ändert lediglich den Typ des Wertes, der als Verweis auf das Objekt verwendet wird. Weitere Informationen finden Sie unter [Polymorphie](../classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Typkonvertierungsausnahmen zur Laufzeit

 In manchen Verweistypkonvertierungen kann der Compiler nicht bestimmen, ob eine Umwandlung zulässig wäre. Es ist möglich, dass ein Umwandlungsvorgang, der ordnungsgemäß kompiliert, zur Laufzeit fehlschlägt. Eine fehlgeschlagene Typumwandlung zur Laufzeit löst wie in folgendem Beispiel dargestellt eine <xref:System.InvalidCastException> aus.  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 C# stellt den [is](../../language-reference/operators/type-testing-and-cast.md#is-operator)-Operator bereit, sodass Sie die Kompatibilität prüfen können, bevor Sie die Umwandlung tatsächlich ausführen. Weitere Informationen finden Sie unter [Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „as“ und „is“](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Konvertierungen](~/_csharplang/spec/conversions.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Typen](./index.md)
- [cast-Operator ()](../../language-reference/operators/type-testing-and-cast.md#cast-operator-)
- [Benutzerdefinierte Konvertierungsoperatoren](../../language-reference/operators/user-defined-conversion-operators.md)
- [Verallgemeinerte Typkonvertierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))
- [Konvertieren einer Zeichenfolge in eine Zahl](./how-to-convert-a-string-to-a-number.md)
