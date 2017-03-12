---
title: "dynamic (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "dynamic_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dynamisch [C#]"
  - "dynamic-Schlüsselwort [C#]"
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# dynamic (C#-Referenz)
Der `dynamic`\-Typ ermöglicht die Vorgänge, in denen die Überprüfung des Kompilierzeittyps umgangen wird.  Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst.  Der `dynamic`\-Typ vereinfacht den Zugriff auf COM\-APIs wie Office\-Automatisierungs\-APIs und zudem auf dynamische APIs wie IronPython\-Bibliotheken und auf das HTML\-Dokumentobjektmodell \(DOM\).  
  
 Der Typ `dynamic` verhält sich in den meisten Umständen wie der Typ `object`.  Vorgänge, die Ausdrücke vom Typ `dynamic` enthalten, werden jedoch nicht aufgelöst, oder der Compiler führt keine Typüberprüfung aus.  Der Compiler verpackt Informationen zum Vorgang, und diese Informationen werden später dazu verwendet, den Vorgang zur Laufzeit auszuwerten.  Als Teil des Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert.  Daher ist der `dynamic`\-Typ nur zur Kompilierzeit vorhanden, jedoch nicht zur Laufzeit.  
  
 Im folgenden Beispiel wird eine Variable vom Typ `dynamic` einer Variable vom Typ `object` gegenüber gestellt.  Um zur Kompilierzeit den Typ jeder Variable zu überprüfen, setzen Sie den Mauszeiger in den `WriteLine`\-Anweisungen über `dyn` oder `obj`.  IntelliSense zeigt **dynamisch** für `dyn` und **Objekt** für `obj` an.  
  
 [!code-cs[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/csharp/dynamic_1.cs)]  
  
 Die `WriteLine`\-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj` an.  An diesem Punkt haben beide den gleichen Typ, ganze Zahl.  Die folgende Ausgabe wird generiert:  
  
 `System.Int32`  
  
 `System.Int32`  
  
 Um zur Kompilierzeit den Unterschied zwischen `dyn` und `obj` zu erkennen, fügen Sie die folgenden zwei Zeilen zwischen den Deklarationen und den `WriteLine`\-Anweisungen im vorherigen Beispiel hinzu.  
  
```c#  
dyn = dyn + 3;  
obj = obj + 3;  
  
```  
  
 Ein Compilerfehler wird gemeldet für die versuchte Hinzufügung einer ganzen Zahl und eines Objekts in Ausdruck `obj + 3`.  Für `dyn + 3` wird jedoch kein Fehler gemeldet.  Der Ausdruck, der `dyn` enthält, wird zur Kompilierzeit nicht überprüft, da der Typ von `dyn``dynamic` ist.  
  
## Kontext  
 Das `dynamic`\-Schlüsselwort kann in den folgenden Situationen direkt oder als Komponente eines konstruierten Typs angezeigt werden:  
  
-   In Deklarationen als Typ einer Eigenschaft, eines Felds, eines Indexers, eines Parameters, eines Rückgabewerts, einer lokalen Variablen oder einer Typeinschränkung.  Die folgende Klassendefinition verwendet `dynamic` in mehreren anderen Deklarationen.  
  
     [!code-cs[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/csharp/dynamic_2.cs)]  
  
-   In expliziten Typkonvertierungen als Zieltyp einer Konvertierung.  
  
     [!code-cs[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/csharp/dynamic_3.cs)]  
  
-   In einem beliebigen Kontext, in dem Typen als Werte dienen, z. B. auf der rechten Seite eines `is`\-Operators oder eines `as`\-Operators, oder als Argument für `typeof` als Teil eines konstruierten Typs.  Beispielsweise kann `dynamic` in den folgenden Ausdrücken verwendet werden.  
  
     [!code-cs[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/csharp/dynamic_4.cs)]  
  
## Beispiel  
 Im folgenden Beispiel wird `dynamic` in mehreren Deklarationen verwendet.  Die `Main`\-Methode stellt auch die Überprüfung von Kompilier\- und Laufzeittyp einander gegenüber.  
  
 [!code-cs[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/csharp/dynamic_5.cs)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
## Siehe auch  
 <xref:System.Dynamic.ExpandoObject?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [object](../../../csharp/language-reference/keywords/object.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is"](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)   
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)