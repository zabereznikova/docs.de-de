---
title: "Werttypen (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.valuetypes"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Werttypen"
  - "Typen [C#], Werttypen"
  - "Werttypen [C#]"
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Werttypen (C#-Referenz)
Die Werttypen sind in zwei Hauptgruppen unterteilt:  
  
-   [Strukturen](../../../csharp/language-reference/keywords/struct.md)  
  
-   [Enumerationen](../../../csharp/language-reference/keywords/enum.md)  
  
 Strukturen lassen sich in die folgenden Kategorien einteilen:  
  
-   Numerische Typen  
  
    -   [Ganzzahlige Typen](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [Gleitkommatypen](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [decimal](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [bool](../../../csharp/language-reference/keywords/bool.md)  
  
-   Benutzerdefinierte Strukturen.  
  
## Hauptfeatures von Werttypen  
 Auf Werttypen basierende Variablen enthalten die tatsächlichen Werte.  Wenn Sie eine Werttypvariable einer anderen zuweisen, wird der enthaltene Wert kopiert.  Beim Zuweisen von Verweistypvariablen ist dies anders. Hierbei wird ein Verweis auf das Objekt kopiert, aber nicht das Objekt selbst.  
  
 Alle Werttypen werden implizit von <xref:System.ValueType?displayProperty=fullName> abgeleitet.  
  
 Anders als bei Verweistypen können Sie einen neuen Typ nicht von einem Werttyp ableiten.  Genauso wie Verweistypen sind Strukturen jedoch in der Lage, Schnittstellen zu implementieren.  
  
 Im Gegensatz zu Verweistypen kann ein Werttyp den `null`\-Wert nicht enthalten.  Allerdings können die [Typ, der NULL\-Werte zulässt,](../../../csharp/programming-guide/nullable-types/index.md)\-Funktion zugewiesen werden auf die `null`\-Werttypen.  
  
 Jeder Werttyp verfügt über einen impliziten Standardkonstruktor, durch den der Standardwert dieses Typs initialisiert wird.  Weitere Informationen zu Standardwerten für Werttypen finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## Hauptfeatures von einfachen Typen  
 Alle diese \(in C\# integrierten\) einfachen Typen sind Aliase der .NET Framework System\-Typen.  Beispielsweise ist [int](../../../csharp/language-reference/keywords/int.md) ein Alias von <xref:System.Int32?displayProperty=fullName>.  Eine vollständige Liste der Aliase finden Sie unter [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md).  
  
 Konstantenausdrücke, deren Operanden ausnahmslos Konstanten einfachen Typs sind, werden während der Kompilierung ausgewertet.  
  
 Einfache Typen können mit Literalen initialisiert werden.  "A" ist beispielsweise ein Literal des Typs `char`, und "2001" ist ein Literal des Typs `int`.  
  
## Initialisieren von Werttypen  
 Lokale Variablen in C\# können erst nach ihrer Initialisierung verwendet werden.  Sie können eine lokale Variable ohne Initialisierung deklarieren, wie im folgenden Beispiel gezeigt:  
  
```  
int myInt;  
```  
  
 Die Variable kann jedoch erst nach ihrer Initialisierung verwendet werden.  Sie können die Variable mithilfe der folgenden Anweisung initialisieren:  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 Diese Anweisung entspricht der folgenden Anweisung:  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 Die Deklaration und die Initialisierung können aber auch über dieselbe Anweisung erfolgen. Beispiel:  
  
```  
int myInt = new int();  
```  
  
 \- oder \-  
  
```  
int myInt = 0;  
```  
  
 Mit dem Operator [new](../../../csharp/language-reference/keywords/new.md) wird der Standardkonstruktor des spezifischen Typs aufgerufen und der Variablen der Standardwert zugewiesen.  Im vorangehenden Beispiel wurde `myInt` vom Standardkonstruktor der Wert `0` zugewiesen.  Weitere Informationen zu Werten, die durch den Aufruf von Standardkonstruktoren zugewiesen werden, finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Bei benutzerdefinierten Typen verwenden Sie [new](../../../csharp/language-reference/keywords/new.md), um den Standardkonstruktor aufzurufen.  Durch die folgende Anweisung wird beispielsweise der Standardkonstruktor der `Point`\-Struktur aufgerufen:  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 Nach diesem Aufruf gilt die Struktur als definitiv zugewiesen, d. h., alle Member werden mit ihren Standardwerten initialisiert.  
  
 Weitere Informationen zum Operator "new" finden Sie unter [new](../../../csharp/language-reference/keywords/new.md).  
  
 Informationen zum Formatieren der Ausgabe numerischer Typen finden Sie unter [Tabelle zur Formatierung numerischer Ergebnisse](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Referenztabellen für Typen](../../../csharp/language-reference/keywords/reference-tables-for-types.md)   
 [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)