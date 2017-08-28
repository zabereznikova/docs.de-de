---
title: float (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- float
- float_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- float keyword [C#]
- floating-point numbers [C#], float keyword
ms.assetid: 1e77db7b-dedb-48b7-8dd1-b055e96a9258
caps.latest.revision: 24
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2f1fb02f84de504112eee826dbee1275fa3ccb7a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="float-c-reference"></a>float (C#-Referenz)
Das `float`-Schlüsselwort kennzeichnet einen einfachen Typ, der 32-Bit-Gleitkommawerte speichert. Die folgende Tabelle zeigt die Genauigkeit und den ungefähren Bereich für den `float`-Typ an.  
  
|Typ|Ungefährer Bereich|Genauigkeit|.NET Framework-Typ|  
|----------|-----------------------|---------------|-------------------------|  
|`float`|-3.4 × 10<sup>38</sup> bis + 3.4 × 10<sup>38</sup>|7 Stellen|<xref:System.Single?displayProperty=fullName>|  
  
## <a name="literals"></a>Literale  
 Ein echtes numerisches Literal auf der rechten Seite des Zuweisungsoperators wird standardmäßig als [Double-Datentyp](double.md) behandelt. Verwenden Sie daher zum Initialisieren einer Float-Variablen die Suffixe `f` oder `F`, wie im folgenden Beispiel:  
  
```csharp
float x = 3.5F;  
```
  
 Wenn Sie das Suffix in der vorherigen Deklaration nicht verwenden, erhalten Sie einen Kompilierungsfehler, da ein [double](double.md)-Wert in einer `float`-Variablen gespeichert werden soll.  
  
## <a name="conversions"></a>Konvertierungen  
 Sie können numerische ganzzahlige Typen und Gleitkommatypen in einem Ausdruck kombinieren. In diesem Fall werden die ganzzahligen Typen in Gleitkommatypen konvertiert. Die Auswertung des Ausdrucks erfolgt gemäß den folgenden Regeln:  
  
-   Wenn einer der Gleitkommatypen ein [double](double.md) ist, wertet der Ausdruck in relationalen oder booleschen Ausdrücken nach [double](double.md) oder [bool](bool.md) aus.  
  
-   Wenn es im Ausdruck keinen [Double-Datentypen](double.md) gibt, wertet der Ausdruck in relationalen oder booleschen Ausdrücken nach `float` oder [bool](bool.md) aus.  
  
 Ein Gleitkomma-Ausdruck kann die folgenden Sätze von Werten enthalten:  
  
-   Positiv und negativ 0 (null)  
  
-   Positiv und negativ unendlich  
  
-   Not-a-Number-Wert (NaN)  
  
-   Die begrenzte Menge von Werten ungleich Null  
  
 Weitere Informationen zu diesen Werten finden Sie im IEEE-Standard für binäre Gleitkommaarithmetik auf der [IEEE](http://go.microsoft.com/fwlink/?LinkId=26269)-Website.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden ein [int](int.md)-, ein [short](short.md) und ein `float`-Datentyp in einem mathematischen Ausdruck verwendet, der ein `float`-Ergebnis aufweist. (Beachten Sie, dass `float` ein Alias für den Typ <xref:System.Single?displayProperty=fullName> ist.) Beachten Sie auch, dass es in diesem Ausdruck keine [Double-Datentypen](double.md) gibt.  
  
 [!code-cs[csrefKeywordsTypes#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/float_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Single>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md)   
 [C#-Schlüsselwörter](index.md)   
 [Tabelle ganzzahliger Typen](integral-types-table.md)   
 [Tabelle integrierter Typen](built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)

