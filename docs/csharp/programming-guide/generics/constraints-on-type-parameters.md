---
title: "Einschränkungen für Typparameter (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
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
ms.openlocfilehash: e91ae026bd89a6dd30b4c9233da4dd897928291e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Einschränkungen für Typparameter (C#-Programmierhandbuch)
Wenn Sie eine generische Klasse definieren, können Sie Beschränkungen auf die Arten der Typen anwenden, die Clientcode für generische Typargumente verwenden kann, wenn er Ihre Klasse instanziiert. Wenn Clientcode versucht, Ihre Klasse zu instanziieren, indem er einen Typ verwendet, der durch Ihre Einschränkung nicht erlaubt ist, kommt es zu einem Kompilierzeitfehler. Diese Einschränkungen werden als Constraints bezeichnet. Constraints werden mit dem kontextuellen Schlüsselwort `where` angegeben. In der folgenden Tabelle werden die sechs verschiedenen Contrainttypen aufgelistet:  
  
|Constraint|Beschreibung|  
|----------------|-----------------|  
|where T: struct|Das Typargument muss ein Werttyp sein. Jeder Werttyp außer <xref:System.Nullable> kann angegeben werden. Weitere Informationen finden Sie unter [Using Nullable Types (Verwenden von Nullable-Typen)](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).|  
|where T : class|Das Typargument muss ein Verweistyp sein. Dies gilt ebenfalls für Klassen-, Schnittstellen-, Delegat- oder Arraytypen.|  
|where T : new()|Das Typargument muss einen öffentlichen, parameterlosen Konstruktor aufweisen. Beim gemeinsamen Verwenden anderen Constraints muss der `new()`-Constraint zuletzt angegeben werden.|  
|where T : \<basisklassenname>|Das Typargument muss die angegebene Basisklasse sein oder von dieser abgeleitet werden.|  
|where T : \<schnittstellenname>|Das Typargument muss die angegebene Schnittstelle sein oder diese implementieren. Es können mehrere Schnittstelleneinschränkungen angegeben werden. Die einschränkende Schnittstelle kann auch generisch sein.|  
|where T : U|Das Typargument, das für T angegeben wurde, muss das für T angegebene Argument sein oder von diesem abgeleitet werden.|  
  
## <a name="why-use-constraints"></a>Weshalb Constraints?  
 Wenn Sie untersuchen möchten, ob ein bestimmtes Argument in einer generischen Liste gültig ist oder es mit einem anderen Element vergleichen möchten, muss der Compiler eine Garantie haben, dass der Operator oder die Methode, die er aufgerufen hat, von jedem Typargument unterstützt wird, das von Clientcode angegeben werden kann. Diese Garantie wird gegeben, indem Sie einen oder mehrere Constraints auf Ihre generische Klassendefinition anwenden. Der Basisklassenconstraint sagt dem Compiler z.B., dass nur Objekte dieses Typs oder Objekte, die von diesem Typ abgeleitet werden, als Typargumente verwendet werden. Sobald der Compiler diese Garantie hat, kann er erlauben, dass Methoden dieses Typs in der generischen Klasse aufgerufen werden können. Constraints werden mit dem kontextuellen Schlüsselwort `where` angewendet. Im folgenden Codebeispiel wird die Funktionalität veranschaulicht, die der `GenericList<T>`-Klasse durch das Anwenden eines Basisklassenconstraints hinzugefügt werden kann (in [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)).  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 Mit dem Constraint kann die generische Klasse die `Employee.Name`-Eigenschaft verwenden, da alle Elemente des Typs T sicher ein `Employee`-Objekt oder ein Objekt, das von `Employee` erbt, sind.  
  
 Mehrere Constraints können wie folgt auf den gleichen Typenparameter angewendet werden, und die Contraints können selbst generische Typen sein:  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 Indem Sie den Typparameter einschränken, erhöhen Sie die Zahl an zulässigen Vorgängen und Methodenaufrufen von denjenigen, die vom einschränkenden Typ und allen Typen in dessen Vererbungshierarchie unterstützt werden. Beim Entwerfen generischer Klassen und Methoden müssen Sie Constraints auf den Typparameter anwenden, wenn Sie Vorgänge mit den generischen Membern durchführen möchten, die über das einfache Zuweisen und Aufrufen von Methoden hinausgehen, die nicht von `System.Object` unterstützt werden.  
  
 Wenn Sie den Constraint `where T : class` anwenden, vermeiden Sie das Verwenden der Operatoren `==` und `!=` mit dem Typparameter, da diese nur auf Verweisidentität und nicht auf Wertgleichheit prüfen. Dies ist auch der Fall, wenn diese Operatoren in einem Typ überladen werden, der als Argument verwendet wird. Der folgende Code veranschaulicht diesen Aspekt. Die Ausgabe ist FALSE, obwohl die <xref:System.String>-Klasse den `==`-Operator überlädt.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 Dieses Verhalten tritt auf, da der Compiler zur Kompilierzeit nur weiß, dass T ein Verweistyp ist, und deshalb die Standardoperatoren verwenden muss, die für alle Verweistypen zulässig sind. Wenn Sie auf Wertgleichheit prüfen müssen, wird empfohlen, dass Sie den `where T : IComparable<T>`-Constraint anwenden und die Schnittstelle in jeder Klasse implementieren, die verwendet wird, um die generische Klasse zu erstellen.  
  
## <a name="constraining-multiple-parameters"></a>Einschränken mehrerer Parameter  
 Sie können wie im folgenden Beispiel gezeigt Constraints auf mehrere Parameter und mehrere Constraints auf einen einzelnen Parameter anwenden:  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a>Ungebundene Typparameter  
 Typparameter, auf die keine Constraints angewendet wurden, wie z.B. T in der öffentlichen Klasse `SampleClass<T>{}`, werden als ungebundene Typparameter bezeichnet. Für ungebundene Typparameter gelten die folgenden Regeln:  
  
-   Die Operatoren `!=` und `==` können nicht verwendet werden, weil es keine Garantie gibt, dass das jeweilige Typargument diese auch unterstützt.  
  
-   Sie können in und aus `System.Object` oder implizit in einen Schnittstellentyp konvertiert werden.  
  
-   Sie können mit [NULL](../../../csharp/language-reference/keywords/null.md) vergleichen. Wenn ein ungebundener Parameter mit `null` verglichen wird, gibt der Vergleich immer FALSE zurück, wenn das Typargument ein Werttyp ist.  
  
## <a name="type-parameters-as-constraints"></a>Typparameter als Constraints  
 Es ist nützlich, einen Typparameter wie in folgendem Beispiel gezeigt als Constraint zu verwenden, wenn eine Memberfunktion mit ihren eigenen Typparametern diesen Parameter auf den Typparameter des enthaltenden Typs einschränken muss:  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 Im vorherigen Beispiel ist `T` ein Typconstraint im Kontext der `Add`-Methode und ein ungebundener Typparameter im Kontext der `List`-Klasse.  
  
 Typparameter können auch in generischen Klassendefinitionen als Constraints verwendet werden. Beachten Sie, dass Typparameter in spitzen Klammern zusammen mit allen anderen Typparametern deklariert werden müssen.  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 Das Verwenden von Typparametern als Constraints für generische Klassen ist nur bis zu einem gewissen Punkt nützlich, da der Compiler keine Informationen über den Typparameter annehmen kann, nur dass er von `System.Object` abgeleitet ist. Sie sollten Typparameter als Constraints dann verwenden, wenn Sie eine Vererbungsbeziehung zwischen zwei Typparametern erzwingen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)   
 [new-Einschränkung](../../../csharp/language-reference/keywords/new-constraint.md)

