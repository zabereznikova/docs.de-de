---
title: "Typen, die NULL-Werte zulassen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Typen mit Nullwert"
  - "Typen, die NULL-Werte zulassen [C#]"
  - "Typen [C#], Mit Nullwert"
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 44
---
# Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)
Typen, die NULL\-Werte zulassen, sind Instanzen der <xref:System.Nullable%601?displayProperty=fullName>\-Struktur.  Ein Typ, der NULL\-Werte zulässt, kann für seinen zugrunde liegenden Werttyp den korrekten Wertebereich darstellen, darüber hinaus aber auch einen zusätzlichen `null`\-Wert.  Einem Typ `Nullable<Int32>`, gesprochen "Nullable of Int32", kann z. B. jeder Wert im Bereich von \-2147483648 bis 2147483647 oder der `null`\-Wert zugewiesen werden.  Einem `Nullable<bool>`\-Typ können die Werte [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) oder [null](../../../csharp/language-reference/keywords/null.md) zugewiesen werden.  Die Möglichkeit, numerischen und booleschen Typen `null`\-Werte zuzuweisen, ist besonders hilfreich beim Umgang mit Datenbanken und anderen Datentypen, die Elemente enthalten, denen unter Umständen kein Wert zugewiesen werden kann.  Ein boolesches Feld in einer Datenbank kann z. B. die Werte `true` oder `false` speichern, oder es wird nicht definiert.  
  
 [!code-cs[csProgGuideTypes#3](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/index_1.cs)]  
  
 Im Beispiel wird die Ausgabe angezeigt:  
  
 `num = Null`  
  
 `Nullable object must have a value.`  
  
 Weitere Beispiele finden Sie unter [Verwenden von auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
## Übersicht über Typen, die NULL\-Werte zulassen  
 Typen, die NULL\-Werte zulassen, weisen die folgenden Eigenschaften auf:  
  
-   Typen, die NULL\-Werte zulassen, stellen Werttypvariablen dar, denen der Wert `null` zugewiesen werden kann.  Sie können keinen auf einem Referenztyp basierenden Typ erstellen, der NULL\-Werte zulässt.  \(Referenztypen unterstützen bereits den `null`\-Wert.\)  
  
-   Die Syntax `T?` ist die Kurzform für <xref:System.Nullable%601>, wobei `T` ein Werttyp ist.  Diese beiden Formen sind austauschbar.  
  
-   Die Zuweisung eines Werts zu einem Typ, der NULL\-Werte zulässt, erfolgt auf die gleiche Art und Weise wie bei regulären Werttypen, z. B. `int? x = 10;` oder `double? d = 4.108`.  Einem Typ, der NULL\-Werte zulässt, kann auch folgender Wert zugewiesen werden: `null`: `int? x = null.`  
  
-   Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName>\-Methode, um den zugewiesenen Wert oder den Standardwert für den zugrunde liegenden Typ zurückzugeben, wenn der Wert `null` ist, z. B.  `int j = x.GetValueOrDefault();`.  
  
-   Verwenden Sie die schreibgeschützten Eigenschaften <xref:System.Nullable%601.HasValue%2A> und <xref:System.Nullable%601.Value%2A>, um den Wert auf NULL zu testen und ihn abzurufen, wie im folgenden Beispiel gezeigt: `if(x.HasValue) j = x.Value;`.  
  
    -   Die `HasValue`\-Eigenschaft gibt `true` zurück, wenn die Variable einen Wert enthält, oder `false`, wenn sie `null` ist.  
  
    -   Die `Value`\-Eigenschaft gibt einen Wert zurück, sofern ein Wert zugewiesen ist.  Andernfalls wird eine <xref:System.InvalidOperationException?displayProperty=fullName> ausgelöst.  
  
    -   Der Standardwert für `HasValue` lautet `false`.  Die `Value`\-Eigenschaft verfügt über keinen Standardwert.  
  
    -   Sie können auch die Operatoren `!=` und `==` mit einem Nullable\-Typ verwenden, wie im folgenden Beispiel gezeigt: `if (x != null) y = x;`.  
  
-   Verwenden Sie den Operator `??` zum Zuweisen eines Standardwerts, der angewendet wird, wenn ein Typ, der `null`\-Werte zulässt und dessen aktueller Wert NULL ist, einem Typ zugewiesen wird, der keine NULL\-Werte zulässt, z. B. `int? x = null; int y = x ?? -1;`.  
  
-   Geschachtelte Typen, die NULL\-Werte zulassen, sind nicht zulässig.  Die folgende Zeile wird nicht kompiliert: `Nullable<Nullable<int>> n;`  
  
## Verwandte Abschnitte  
 Weitere Informationen:  
  
-   [Verwenden von auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [Boxing von Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [?? Operator](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Nullable>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#](../../../csharp/csharp.md)   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Was geschieht genau "transformierter" Durchschnitt?](http://go.microsoft.com/fwlink/?LinkId=112382)