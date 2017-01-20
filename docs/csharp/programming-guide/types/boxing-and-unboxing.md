---
title: "Boxing und Unboxing (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "cs.boxing"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Boxing"
  - "C#-Sprache, Unboxing"
  - "Unboxing [C#]"
  - "Boxing [C#]"
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 34
caps.handback.revision: 34
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Boxing und Unboxing (C#-Programmierhandbuch)
Beim Boxing handelt es sich um die Konvertierung eines [Werttyps](../../../csharp/language-reference/keywords/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird.  Wenn die CLR einen Werttyp schachtelt, wird der Wert in einem System.Object geschachtelt und im verwalteten Heap gespeichert.  Durch Unboxing wird der Werttyp aus dem Objekt extrahiert.  Boxing ist implizit, Unboxing ist explizit.  Das Konzept von Boxing und Unboxing unterliegt der einheitlichen C\#\-Ansicht des Typsystems, in dem ein Wert eines beliebigen Typs als Objekt behandelt werden kann.  
  
 Im folgenden Beispiel wird die Ganzzahlvariable `i` mittels *Boxing* konvertiert und dem Objekt `o` zugewiesen.  
  
 [!code-cs[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]  
  
 Das Objekt `o`  kann dann mittels Unboxing zurückkonvertiert und der Ganzzahlvariablen `i` zugewiesen werden:  
  
 [!code-cs[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]  
  
 Die folgenden Beispiele veranschaulichen, wie Boxing in C\# verwendet wird.  
  
 [!code-cs[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]  
  
## Leistung  
 Im Verhältnis zu einfachen Zuweisungen sind Boxing und Unboxing rechentechnisch aufwändige Prozesse.  Wenn ein Werttyp mittels Boxing konvertiert wird, muss ein neues Objekt zugeordnet und erstellt werden.  Die für Unboxing erforderliche Umwandlung ist ebenfalls, jedoch in geringerem Maße rechentechnisch aufwändig.  Weitere Informationen finden Sie unter [Leistung](../Topic/.NET%20Performance%20Tips.md).  
  
## Boxing  
 Boxing wird verwendet, um Werttypen im Heap der Garbage Collection zu speichern.  Beim Boxing handelt es sich um die implizite Konvertierung eines [Werttyps](../../../csharp/language-reference/keywords/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird.  Beim Boxing eines Werttyps wird auf dem Heap eine Objektinstanz zugeordnet. Anschließend wird der Wert in das neue Objekt kopiert.  
  
 Beachten Sie die folgende Deklaration einer Werttypvariablen:  
  
 [!code-cs[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]  
  
 Mit der folgenden Anweisung wird der Boxing\-Vorgang implizit auf die Variable `i` angewendet:  
  
 [!code-cs[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]  
  
 Diese Anweisung bewirkt, dass der Objektverweis `o` auf dem Stapel erstellt wird, der auf einen Wert vom Typ `int` auf dem Heap verweist.  Dieser Wert ist eine Kopie des Werttyps, der der Variablen `i` zugewiesen ist.  In der folgenden Abbildung ist der Unterschied zwischen den Variablen `i` und `o` dargestellt.  
  
 ![BoxingConversion&#45;Grafik](../../../csharp/programming-guide/types/media/vcboxingconversion.png "vcBoxingConversion")  
Boxing\-Konvertierung  
  
 Es auch möglich, das Boxing wie im folgenden Beispiel explizit auszuführen. Explizites Boxing ist jedoch nie erforderlich:  
  
 [!code-cs[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]  
  
## Beschreibung  
 In diesem Beispiel wird die Ganzzahlvariable `i` mittels Boxing in das Objekt `o` konvertiert.  Anschließend wird der in der Variablen `i` gespeicherte Wert von `123` in `456` geändert.  Das Beispiel veranschaulicht, dass der ursprüngliche Werttyp und das durch Boxing entstehende Objekt unterschiedliche Speicherorte verwenden und daher verschiedene Werte speichern können.  
  
## Beispiel  
 [!code-cs[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]  
  
## Unboxing  
 Beim Unboxing handelt es sich um eine explizite Konvertierung vom `object`\-Typ in einen [Werttyp](../../../csharp/language-reference/keywords/value-types.md) bzw. von einem Schnittstellentyp in einen Werttyp, in dem die Schnittstelle implementiert wird.  Ein Unboxing\-Vorgang umfasst folgende Schritte:  
  
-   Überprüfen der Objektinstanz, um sicherzustellen, dass es sich um einen mittels Boxing "verpackten" Wert des jeweiligen Werttyps handelt.  
  
-   Kopieren des Werts aus der Instanz in die Werttypvariable.  
  
 Anhand der folgenden Anweisungen werden sowohl Boxing\-Vorgänge als auch Unboxing\-Vorgänge veranschaulicht:  
  
 [!code-cs[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]  
  
 In der folgenden Abbildung ist das Ergebnis der vorherigen Anweisungen dargestellt.  
  
 ![Grafik zur UnBoxing&#45;Konvertierung](../../../csharp/programming-guide/types/media/vcunboxingconversion.png "vcUnBoxingConversion")  
Unboxing\-Konvertierung  
  
 Damit das Unboxing eines Werttypen zur Laufzeit erfolgreich verläuft, muss das zu konvertierende Element ein Verweis auf ein Objekt sein, das zuvor durch Boxing einer Instanz dieses Werttyps erstellt wurde.  Der Versuch, ein Unboxing durchzuführen, `null` löst ein <xref:System.NullReferenceException> aus.  Der Versuch, einen Verweis auf einen nicht kompatiblen Werttyp mittels Unboxing zu konvertieren, führt zu einer <xref:System.InvalidCastException>.  
  
## Beispiel  
 Im folgenden Beispiel wird ein Fall von ungültigem Unboxing und der sich daraus ergebenden `InvalidCastException` veranschaulicht.  Bei Verwendung von `try` und `catch` wird eine Fehlermeldung angezeigt, wenn der Fehler auftritt.  
  
 [!code-cs[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]  
  
 Dieses Programm gibt Folgendes aus:  
  
 `Specified cast is not valid.  Error: Incorrect unboxing.`  
  
 Wenn Sie die Anweisung  
  
```  
int j = (short) o;  
```  
  
 in:  
  
```  
int j = (int) o;  
```  
  
 ändern, wird die Konvertierung ausgeführt und Folgendes ausgegeben.  
  
 `Unboxing OK.`  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
-   [Verweistypen](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [Werttypen](../../../csharp/language-reference/keywords/value-types.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)