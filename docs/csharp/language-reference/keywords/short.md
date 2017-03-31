---
title: short (C#-Referenz) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3c14ae463021fbeed9de24610292fa7516a453fe
ms.lasthandoff: 03/13/2017

---
# <a name="short-c-reference"></a>short (C#-Referenz)
Das Schlüsselwort `short` kennzeichnet einen ganzzahligen Datentyp, der Werte anhand der Größe und des Bereichs speichert, die in der folgenden Tabelle gezeigt werden.  
  
|Typ|Bereich|Größe|.NET Framework-Typ|  
|----------|-----------|----------|-------------------------|  
|`short`|–32.768 bis 32.767|Ganze 16-Bit-Zahl mit Vorzeichen|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a>Literale  
 Sie können eine Variable `short` wie im folgenden Beispiel deklarieren und initialisieren:  
  
```  
  
short x = 32767;  
```  
  
 In der vorherigen Deklaration wird das Ganzzahlliteral `32767` implizit von [int](../../../csharp/language-reference/keywords/int.md) zu `short` konvertiert. Wenn das Ganzzahlliteral nicht in einen `short`-Speicherort passt, wird ein Kompilierungsfehler ausgelöst.  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung durchgeführt werden. Betrachten Sie z.B. die folgenden überladenen Methoden, die die Parameter `short` und [int](../../../csharp/language-reference/keywords/int.md) verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Die Verwendung der `short`-Umwandlung gewährleistet, dass der richtige Typ aufgerufen wird, wie z.B.:  
  
```  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a>Konvertierungen  
 Es gibt eine vordefinierte implizite Konvertierung von `short` in [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Sie können numerische nonliteral-Typen einer größeren Speichergröße nicht implizit in `short` konvertieren (siehe [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) für die Speichergrößen ganzzahliger Typen). Betrachten Sie z.B. die folgenden beiden `short`-Variablen `x` und `y`:  
  
```  
  
short x = 5, y = 12;  
```  
  
 Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig [int](../../../csharp/language-reference/keywords/int.md) ergibt.  
  
 `short`   `z = x + y;   // Error: no conversion from int to short`  
  
 Verwenden Sie eine Umwandlung, um dieses Problem zu lösen:  
  
 `short`   `z = (`  `short`  `)(x + y);   // OK: explicit conversion`  
  
 Es ist jedoch möglich, die folgenden Anweisungen zu verwenden, bei denen die Zielvariable über dieselbe oder eine größere Speichergröße verfügt:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Es gibt keine implizite Konvertierung von Gleitkommadatentypen zu `short`. Die folgende Anweisung erzeugt z.B. einen Compilerfehler, außer es wird eine explizite Umwandlung verwendet:  
  
```  
  
      short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Informationen zu arithmetischen Ausdrücken mit Gleitkomma- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Int16>   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
