---
title: "short (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "short"
  - "short_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "short-Schlüsselwort [C#]"
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# short (C#-Referenz)
Das `short`\-Schlüsselwort kennzeichnet einen ganzzahligen Datentyp, in dem Werte entsprechend der Größe und dem Bereich in der folgenden Tabelle gespeichert werden.  
  
|Typ|Bereich|Größe|.NET Framework\-Typ|  
|---------|-------------|-----------|-------------------------|  
|`short`|\-32.768 bis 32.767|Ganze 16\-Bit\-Zahl mit Vorzeichen|<xref:System.Int16?displayProperty=fullName>|  
  
## Literale  
 Eine `short`\-Variable kann wie im folgenden Beispiel deklariert und initialisiert werden:  
  
```  
  
short x = 32767;  
```  
  
 In der vorangehenden Deklaration wird das Ganzzahlliteral `32767` implizit von [int](../../../csharp/language-reference/keywords/int.md) in `short` konvertiert.  Wenn das Ganzzahlliteral zu groß für einen `short`\-Speicherbereich ist, tritt ein Kompilierungsfehler auf.  
  
 Beim Aufrufen überladener Methoden muss eine Typumwandlung erfolgen.  Betrachten Sie z. B. die folgenden überladenen Methoden, die den `short`\-Parameter und den [int](../../../csharp/language-reference/keywords/int.md)\-Parameter verwenden:  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 Die Verwendung der `short`\-Typumwandlung gewährleistet, dass der richtige Typ aufgerufen wird. Beispiel:  
  
```  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## Konvertierungen  
 Es erfolgt eine vordefinierte implizite Konvertierung von `short` in [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) oder [decimal](../../../csharp/language-reference/keywords/decimal.md).  
  
 Es ist nicht möglich, numerische Typen mit höherer Speichergröße, die keine Literale sind, implizit in `short` zu konvertieren. \(Informationen zu den Speichergrößen ganzzahliger Typen finden Sie unter [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md).\)  Betrachten Sie z. B. die beiden folgenden `short`\-Variablen `x` und `y`:  
  
```  
  
short x = 5, y = 12;  
```  
  
 Die folgende Zuweisungsanweisung erzeugt einen Kompilierungsfehler, da der arithmetische Ausdruck auf der rechten Seite des Zuweisungsoperators standardmäßig den Wert [int](../../../csharp/language-reference/keywords/int.md) annimmt.  
  
 `short`   `z = x + y;   // Error: no conversion from int to short`  
  
 Verwenden Sie zur Problembehebung eine Typumwandlung:  
  
 `short`   `z = (`  `short`  `)(x + y);   // OK: explicit conversion`  
  
 Hier können jedoch die folgenden Anweisungen verwendet werden, bei denen die Zielvariable dieselbe oder eine höhere Speichergröße aufweist:  
  
```  
int m = x + y;  
long n = x + y;  
```  
  
 Gleitkommatypen werden nicht implizit in `short` konvertiert.  Durch die folgende Anweisung wird z. B. ein Compilerfehler erzeugt, sofern keine explizite Typumwandlung stattfindet:  
  
```  
  
        short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 Weitere Informationen über arithmetische Ausdrücke aus Gleitkomma\- und ganzzahligen Typen finden Sie unter [float](../../../csharp/language-reference/keywords/float.md) und [double](../../../csharp/language-reference/keywords/double.md).  
  
 Weitere Informationen zu impliziten numerischen Konvertierungsregeln finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Int16>   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)