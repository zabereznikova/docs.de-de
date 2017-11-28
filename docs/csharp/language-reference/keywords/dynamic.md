---
title: dynamic (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
caps.latest.revision: "25"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e3bf51ab62e195f7a5d1f0641f62380977c731ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dynamic-c-reference"></a>dynamic (C#-Referenz)
Der `dynamic`-Typ ermöglicht die Vorgänge, in denen er auftritt, um die Typüberprüfung zur Kompilierzeit zu umgehen. Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst. Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z.B. die Office Automation-APIs, und auch auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).  
  
 Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`. Jedoch werden Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft. Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet. Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert. Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.  
  
 Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`. Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen. IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.  
  
 [!code-csharp[csrefKeywordsTypes#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_1.cs)]  
  
 Die `WriteLine`-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`. Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer. Es wird die folgende Ausgabe generiert:  
  
 `System.Int32`  
  
 `System.Int32`  
  
 Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.  
  
```csharp  
dyn = dyn + 3;  
obj = obj + 3;  
```  
  
 Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben. Es wird jedoch kein Fehler für `dyn + 3` gemeldet. Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn` `dynamic` ist.  
  
## <a name="context"></a>Kontext  
 Das Schlüsselwort `dynamic` kann direkt oder als Komponente eines konstruierten Typs in den folgenden Situationen erscheinen:  
  
-   In Deklarationen, als Typ einer Eigenschaft, als Feld, Indexer, Parameter, Rückgabewert, lokale Variable oder Typeinschränkung. Die folgende Klassendefinition verwendet `dynamic` in einigen unterschiedlichen Deklarationen.  
  
     [!code-csharp[csrefKeywordsTypes#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_2.cs)]  
  
-   In expliziten Typkonvertierungen als Zieltyp einer Konversion.  
  
     [!code-csharp[csrefKeywordsTypes#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_3.cs)]  
  
-   In jedem Kontext, in dem Typen als Werte, z.B. auf der rechten Seite eines `is`-Operators oder eines `as`-Operators oder als Argument für `typeof` als Teil eines konstruierten Typs dienen. Zum Beispiel kann `dynamic` in den folgenden Ausdrücken verwendet werden.  
  
     [!code-csharp[csrefKeywordsTypes#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_4.cs)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen. Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.  
  
 [!code-csharp[csrefKeywordsTypes#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/dynamic_5.cs)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
 <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [object](../../../csharp/language-reference/keywords/object.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [as](../../../csharp/language-reference/keywords/as.md)  
 [typeof](../../../csharp/language-reference/keywords/typeof.md)  
 [Gewusst wie: Sichere Umwandlung mit den Operatoren "as" und "is"](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)  
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
