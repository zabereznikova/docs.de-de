---
title: Werttypen (C#-Referenz)
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: baf0db751cd70d50d4cf440626dd405b01c8d7ad
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147716"
---
# <a name="value-types-c-reference"></a>Werttypen (C#-Referenz)

Es gibt zwei Werttypen:

- [Strukturen](struct.md)

- [Enumerationen](enum.md)

## <a name="main-features-of-value-types"></a>Hauptfunktionen von Werttypen

Eine Variable eines Werttyps enthält einen Wert des Typs. Beispielsweise kann eine Variable von Typ `int` den `42`-Wert enthalten. Dies unterscheidet sich von einer Variablen eines Referenztyps, die eine Referenz auf eine Instanz des Typs enthält, auch bekannt als Objekt. Wenn Sie einer Variablen eines Werttyps einen neuen Wert zuweisen, wird der Wert kopiert. Wenn Sie einer Variablen eines Referenztyps einen neuen Wert zuweisen, wird die Referenz kopiert, nicht das Objekt selbst.

Alle Werttypen werden implizit von <xref:System.ValueType?displayProperty=nameWithType> abgeleitet.  
  
Im Gegensatz zu Verweistypen können Sie von Werttypen keinen neuen ableiten. Strukturen können aber wie Verweistypen Schnittstellen implementieren.  
  
Werttypvariablen können nicht standardmäßig `null` sein. Variablen der entsprechenden [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md) können jedoch `null` sein.
  
Jeder Werttyp hat einen impliziten Standardkonstruktor, der den Standardwert dieses Typs initialisiert. Informationen zu den Standardwerten von Werttypen finden Sie unter [Tabelle für Standardwerte](default-values-table.md).  
  
## <a name="simple-types"></a>Einfache Typen

Die *einfachen Typen* sind eine Reihe von vordefinierten Strukturtypen, die von C# bereitgestellt werden, und umfassen die folgenden Typen:

- [Ganzzahltypen](integral-types-table.md): ganzzahlige numerische Typen und der [char](char.md)-Typ
- [Gleitkommatypen](floating-point-types-table.md)
- [bool](bool.md)

Die einfachen Typen werden durch Schlüsselwörter identifiziert, aber diese Schlüsselwörter sind einfach Aliase für vordefinierte Strukturtypen im Namespace <xref:System>. [int](int.md) ist z.B. ein Alias von <xref:System.Int32?displayProperty=nameWithType>. Eine vollständige Liste der Aliase finden Sie unter [Tabelle integrierter Typen](built-in-types-table.md).

Die einfachen Typen unterscheiden sich von anderen Strukturtypen dadurch, dass sie bestimmte zusätzliche Vorgänge ermöglichen:

- Einfache Typen können mithilfe von Literalen initialisiert werden. `'A'` ist beispielsweise ein Literal vom Typ `char`, und `2001` ist ein Literal vom Typ `int`.

- Konstanten der einfachen Typen können Sie mit dem Schlüsselwort [const](const.md) deklarieren. Es ist nicht möglich, Konstanten anderer Strukturtypen zu haben.

- Konstante Ausdrücke, deren Operanden alle einfache Typkonstanten sind, werden zur Kompilierzeit ausgewertet.

Weitere Informationen finden Sie im Abschnitt [Einfache Typen](~/_csharplang/spec/types.md#simple-types) der [C#-Sprachspezifikation](../language-specification/index.md).
  
## <a name="initializing-value-types"></a>Initialisieren von Werttypen

 Lokale Variablen in C# müssen vor ihrer Verwendung initialisiert werden. Sie könnten eine lokale Variable beispielsweise ohne Initialisierung wie im folgenden Beispiel deklarieren:  
  
```csharp  
int myInt;  
```  
  
 Sie können sie nicht verwenden, bis Sie sie initialisiert haben. Sie können sie mit der folgenden Anweisung initialisieren:  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Diese Anweisung entspricht der folgenden Anweisung:  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Natürlich können Sie sich die Deklaration und die Initialisierung in derselben Anweisung befinden, wie in den folgenden Beispielen dargestellt:  
  
```csharp  
int myInt = new int();  
```  
  
 – oder –  
  
```csharp  
int myInt = 0;  
```  
  
 Durch die Verwendung des Operators [new](new.md) wird der Standardkonstruktor des angegebenen Typs aufgerufen und der Variablen der Standardwert zugewiesen. Im vorherigen Beispiel hat der Standardkonstruktor `myInt` den Wert `0` zugewiesen. Weitere Informationen zu Werten, die durch Aufrufen von Standardkonstruktoren zugewiesen werden, finden Sie unter [Tabelle für Standardwerte](default-values-table.md).  
  
 Verwenden Sie bei benutzerdefinierten Typen [new](new.md) zum Aufrufen des Standardkonstruktors. Die folgende Anweisung ruft z.B. den Standardkonstruktor der `Point`-Struktur auf:  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Nach diesem Aufruf gilt die Struktur als definitiv zugewiesen. Das bedeutet, dass alle ihre Member mit ihren Standardwerten initialisiert werden.  
  
 Weitere Informationen zum `new`-Operator finden Sie unter [neu](new.md).  
  
 Informationen zum Formatieren der Ausgabe von numerischen Typen finden Sie unter [Tabelle zur Formatierung numerischer Ergebnisse](formatting-numeric-results-table.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [C#-Schlüsselwörter](index.md)  
- [Typen](types.md)  
- [Referenztabellen für Typen](reference-tables-for-types.md)  
- [Verweistypen](reference-types.md)  
- [Nullable-Typen](../../programming-guide/nullable-types/index.md)  
