---
title: "Einschr&#228;nkungen f&#252;r Typparameter (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Generika [C#], Typeinschränkungen"
  - "Typeinschränkungen [C#]"
  - "Typparameter [C#], Einschränkungen"
  - "Ungebundener Typparameter [C#]"
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
caps.handback.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Einschr&#228;nkungen f&#252;r Typparameter (C#-Programmierhandbuch)
Beim Definieren einer generischen Klasse können Sie Einschränkungen für diejenigen Typen anwenden, die der Clientcode für Typargumente verwenden kann, wenn er die Klasse instanziiert.  Wenn der Clientcode versucht, die Klasse mit einem Typ zu instanziieren, der durch eine Beschränkung nicht zulässig ist, tritt ein Kompilierungsfehler auf.  Diese Beschränkungen heißen Einschränkungen.  Sie werden mit dem `where`\-Kontextschlüsselwort angegeben.  In der folgenden Tabelle werden die sechs Einschränkungstypen aufgelistet:  
  
|Einschränkung|Beschreibung|  
|-------------------|------------------|  
|where T: struct|Das Typargument muss ein Werttyp sein.  Jeder Werttyp außer <xref:System.Nullable> kann angegeben werden.  Weitere Informationen finden Sie unter [Verwenden von auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).|  
|where T : class|Das Typargument muss ein Verweistyp sein. Dies gilt auch für Klassen\-, Schnittstellen\-, Delegat\- und Arraytypen.|  
|where T : new\(\)|Das Typargument muss einen öffentlichen parameterlosen Konstruktor aufweisen.  Wenn Sie die `new()`\-Einschränkung mit anderen Einschränkungen verwenden, muss sie zuletzt angegeben werden.|  
|where T : \<Basisklassenname\>|Das Typargument muss die Basisklasse sein oder daraus abgeleitet sein.|  
|where T : \<Schnittstellenname\>|Das Typargument muss die angegebene Schnittstelle sein oder sie implementieren.  Mehrere Schnittstelleneinschränkungen können angegeben werden.  Die einschränkende Schnittstelle kann auch generisch sein.|  
|where T : U|Das für T angegebene Typargument muss mit dem für U angegebenen Argument übereinstimmen oder davon abgeleitet werden.|  
  
## Gründe für die Verwendung von Einschränkungen  
 Wenn Sie ein Element in einer generischen Liste untersuchen möchten, um seine Gültigkeit zu überprüfen oder um es mit einem anderen Element zu vergleichen, benötigt der Compiler eine Garantie, dass der aufzurufende Operator oder die aufzurufende Methode von den im Clientcode angegebenen Typargumenten unterstützt wird.  Diese Garantie wird durch das Einfügen von Einschränkungen in die generische Klassendefinition erreicht.  Die Basisklasseneinschränkung teilt dem Compiler mit, dass nur Objekte dieses Typs oder aus diesem Typ abgeleitete Objekte als Typargumente verwendet werden.  Sobald der Compiler diese Garantie hat, kann er zulassen, dass Methoden dieses Typs innerhalb der generischen Klasse aufgerufen werden.  Einschränkungen werden mit dem `where`\-Kontextschlüsselwort angegeben.  Im folgenden Codebeispiel werden die Funktionen dargestellt, die einer `GenericList<T>`\-Klasse \(in [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)\) durch Anwenden einer Basisklasseneinschränkung hinzugefügt werden können.  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_1.cs)]  
  
 Die Einschränkung ermöglicht der generischen Klasse die Verwendung der `Employee.Name`\-Eigenschaft, da alle Elemente des Typs T garantiert entweder `Employee`\-Objekte sind oder Objekte, die von `Employee` erben.  
  
 Mehrere Einschränkungen können auf denselben Typparameter angewendet werden, und die Einschränkungen selbst können generische Typen sein:  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_2.cs)]  
  
 Durch das Einschränken des Typparameters erhöhen Sie die Anzahl der zulässigen Operationen und Methodenaufrufe um die Operationen und Methodenaufrufe, die vom Einschränkungstyp und allen Typen in seiner Vererbungshierarchie unterstützt werden.  Wenn Sie Operationen mit generischen Membern durchführen, die über einfache Zuweisungen hinausgehen oder Methoden aufrufen, die nicht von `System.Object` unterstützt werden, sollten Sie daher beim Entwerfen von generischen Klassen und Methoden Einschränkungen auf die Typparameter anwenden.  
  
 Beim Anwenden der `where T : class`\-Einschränkung wird empfohlen, die Operatoren `==` und `!=` nicht für den Typparameter zu verwenden, da diese Operatoren nur die Referenzgleichheit und nicht die Wertgleichheit prüfen.  Dies ist auch dann der Fall, wenn diese Operatoren in einem als Argument verwendeten Typ überladen werden.  Im folgenden Code wird dies veranschaulicht: Die Ausgabe ist false, obwohl die <xref:System.String>\-Klasse den Operator `==` überlädt.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_3.cs)]  
  
 Der Grund für dieses Verhalten ist, dass der Compiler zur Kompilierzeit nur weiß, dass T ein Referenztyp ist. Deswegen muss er die Standardoperatoren verwenden, die für alle Referenztypen gültig sind.  Falls Sie auf Wertgleichheit prüfen müssen, wird empfohlen, die `where T : IComparable<T>`\-Einschränkung anzuwenden und diese Schnittstelle in jeder Klasse zu implementieren, mit der die generische Klasse erstellt wird.  
  
## Einschränken mehrerer Parameter  
 Wie im folgenden Beispiel gezeigt, können Sie eine Einschränkung auf mehrere Parameter, aber auch mehrere Einschränkungen auf einen einzelnen Parameter anwenden:  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_4.cs)]  
  
## Ungebundene Typparameter  
 Typparameter ohne Einschränkungen, z. B. T in der öffentlichen `SampleClass<T>{}`\-Klasse, werden als ungebundene Typparameter bezeichnet.  Ungebundene Typparameter haben die folgenden Regeln:  
  
-   Die Operatoren `!=` und `==` können nicht verwendet werden, weil es keine Garantie gibt, dass das konkrete Typargument diese Operatoren unterstützt.  
  
-   Sie können in und von `System.Object` konvertiert werden oder explizit in einen Schnittstellentyp konvertiert werden.  
  
-   Vergleiche mit [null](../../../csharp/language-reference/keywords/null.md) sind möglich.  Falls ein ungebundener Parameter mit `null` verglichen wird, wird der Vergleich immer false zurückgeben, wenn das Argument ein Werttyp ist.  
  
## Typparameter als Einschränkungen  
 Die Verwendung eines generischen Typparameters als Einschränkung ist nützlich, wenn eine Memberfunktion mit eigenem Typparameter diesen auf den Typparameter des enthaltenden Typs einschränken muss. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_5.cs)]  
  
 Im vorherigen Beispiel ist `T` im Kontext der `Add`\-Methode eine Typeinschränkung und im Kontext der `List`\-Klasse ein ungebundener Typparameter.  
  
 Typparameter können auch als Einschränkungen in generischen Klassendefinitionen verwendet werden.  Beachten Sie, dass der Typparameter in spitzen Klammern zusammen mit allen anderen Typparameter deklariert werden muss:  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-paramet_6.cs)]  
  
 Der Nutzen von Typparametern als Einschränkungen ist bei generischen Klassen sehr begrenzt, weil der Compiler keine Informationen über den Typparameter hat, außer, dass er von `System.Object` abgeleitet ist.  Verwenden Sie Typparameter als Einschränkungen für generische Klassen in Szenarios, in denen Sie eine Vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.  
  
## Siehe auch  
 <xref:System.Collections.Generic>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)   
 [new\-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md)