---
title: decimal (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 336a4a7bb485a48282dd740bafb81421e0cba693
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="decimal-c-reference"></a>decimal (C#-Referenz)
Das `decimal`-Schlüsselwort kennzeichnet einen 128-Bit-Datentyp. Im Vergleich zu Gleitkommatypen verfügt der `decimal`-Typ über höhere Genauigkeit und einen kleineren Wertebereich. Dadurch eignet er sich für Finanz- und Währungskalkulationen. Der folgenden Tabelle können Sie den ungefähren Bereich und die Genauigkeit des `decimal`-Typs entnehmen.  
  
|Typ|Ungefährer Bereich|Genauigkeit|.NET Framework-Typ|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|(-7.9 x 10<sup>28</sup> bis 7.9 x 10<sup>28</sup>) / (10<sup>0 bis 28</sup>)|28-29 signifikante Stellen|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a>Literale  
 Wenn ein echtes numerisches Literal als `decimal` behandelt werden soll, verwenden Sie das Suffix m oder M. Beispiel:  
  
```  
  
decimal myMoney = 300.5m;  
```  
  
 Ohne das Suffix „m“ wird die Zahl als [double](../../../csharp/language-reference/keywords/double.md) behandelt, was zu einem Compilerfehler führt.  
  
## <a name="conversions"></a>Konvertierungen  
 Die ganzzahligen Typen werden implizit in `decimal` konvertiert, und das Ergebnis wird als `decimal` ausgewertet. Aus diesem Grund können Sie eine decimal-Variable mit einem Ganzzahlliteral ohne das Suffix initialisieren. Beispiel:  
  
```  
  
decimal myMoney = 300;  
```  
  
 Es findet keine implizite Konvertierung zwischen Gleitkommatypen und dem `decimal`-Typ statt. Folglich muss die Konvertierung zwischen diesen beiden Typen mittels einer Typumwandlung durchgeführt werden. Zum Beispiel:  
  
```  
  
      decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 `decimal`-Typen und numerische ganzzahlige Typen können auch gemeinsam im selben Ausdruck verwendet werden. Wenn Sie jedoch Gleitkomma- und `decimal`-Typen ohne Typumwandlung in einem Ausdruck verwenden, tritt ein Kompilierungsfehler auf.  
  
 Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
## <a name="formatting-decimal-output"></a>Formatieren von Dezimalausgaben  
 Sie können die Ergebnisse mithilfe der `String.Format`-Methode oder der <xref:System.Console.Write%2A?displayProperty=fullName>-Methode formatieren, durch die `String.Format()` aufgerufen wird. Das Währungsformat wird mit der Standardwährungsformat-Zeichenfolge "C" oder "c" angegeben, wie in Beispiel 2 weiter unten in diesem Artikel dargestellt. Weitere Informationen zur `String.Format`-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=fullName>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Compilerfehler aufgrund des Versuchs verursacht, [Double](../../../csharp/language-reference/keywords/double.md)- und `decimal`-Variablen hinzuzufügen.  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
  
```  
  
 Das Ergebnis ist der folgende Fehler:  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 In diesem Beispiel werden `decimal` und [int](../../../csharp/language-reference/keywords/int.md) in demselben Ausdruck verwendet. Das Ergebnis wird als `decimal`-Typ ausgewertet.  
  
 [!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Ausgabe mit der Währungsformatzeichenfolge formatiert. Beachten Sie, dass `x` gerundet wird, da mehr Dezimalstellen als im Format $0.99 vorhanden sind. Die Variable `y`, die die maximale Anzahl exakter Stellen darstellt, wird genau im richtigen Format angezeigt.  
  
 [!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Decimal>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [Standardmäßige Zahlenformatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md)
