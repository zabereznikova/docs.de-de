---
title: Ausdrücke – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 05/11/2017
helpviewer_keywords:
- expressions [C#]
- C# language, expressions
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
ms.openlocfilehash: e08220362c0acec6060ade75131e34a6b3fb7390
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417692"
---
# <a name="expressions-c-programming-guide"></a>Ausdrücke (C#-Programmierhandbuch)

Ein *Ausdruck* ist eine Sequenz von einem oder mehr Operanden und null oder mehr [Operatoren](../../language-reference/operators/index.md), die einen einzelnen Wert, ein Objekt, eine Methode oder einen Namespace annehmen können. Ausdrücke können einen literalen Wert, einen Methodenaufruf, einen Operator und die entsprechenden Operanden oder einen *einfachen Namen* enthalten. Einfache Namen können der Name einer Variablen, eines Typmembers, eines Methodenparameters, eines Namespaces oder eines Typs sein.  
  
 Ausdrücke können Operatoren verwenden, die wiederum andere Ausdrücke als Parameter oder Methodenaufrufe verwenden können, deren Parameter wiederum andere Methodenaufrufe darstellen. Ausdrücke können also einfach aber auch sehr komplex sein. Nachstehend sind zwei Beispiele für Ausdrücke:  
  
```csharp  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25));

System.Convert.ToInt32("35");  
```  
  
## <a name="expression-values"></a>Ausdruckswerte

 In den meisten Fällen, in denen Ausdrücke verwendet werden, z.B. in Ausdrücken oder Methodenparametern, wird erwartet, dass der Ausdruck einen Wert ergibt. Wenn x und y ganze Zahlen sind, ergibt der Ausdruck `x + y` einen numerischen Wert. Der Ausdruck `new MyClass()` ergibt einen Verweis auf eine neue Instanz einer `MyClass`-Klasse. Der Ausdruck `myClass.ToString()` ergibt eine Zeichenfolge, da dies der Rückgabetyp der Methode ist. Obwohl ein Namespacename jedoch als Ausdruck klassifiziert ist, ergibt er keinen Wert und kann deshalb nie das Endergebnis eines Ausdrucks sein. Sie können keinen Namespacenamen einem Methodenparameter übergeben oder ihn in einem neuen Ausdruck verwenden bzw. ihn einer Variable zuweisen. Sie können ihn nur als Unterausdruck in einem größeren Ausdruck verwenden. Das gleiche gilt auch für Typen (im Unterschied zu <xref:System.Type?displayProperty=nameWithType>-Objekten), Methodengruppennamen (im Unterschied zu bestimmten Methoden) und Ereignisaccessoren [add](../../language-reference/keywords/add.md) und [remove](../../language-reference/keywords/remove.md).  
  
 Jeder Wert verfügt über einen zugeordneten Typ. Wenn z.B. x und y jeweils Variablen vom Typ `int` sind, wird der Wert des Ausdrucks `x + y` auch als `int` geschrieben. Wenn der Wert einer Variable eines anderen Typs zugewiesen ist oder wenn x und y unterschiedliche Typen sind, werden die Regeln der Typkonvertierung angewendet. Weitere Informationen darüber, wie Konvertierungen funktionieren, finden Sie unter [Umwandlung und Typkonvertierungen](../types/casting-and-type-conversions.md).  
  
## <a name="overflows"></a>Überläufe

 Numerische Ausdrücke können zu Überläufen führen, wenn der Wert größer als der Maximalwert des Typs des Werts ist. Weitere Informationen finden Sie unter [Checked und Unchecked](../../language-reference/keywords/checked-and-unchecked.md) und dem Abschnitt [Explizite numerische Konvertierungen](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) des Artikels [Integrierte numerische Konvertierungen](../../language-reference/builtin-types/numeric-conversions.md).
  
## <a name="operator-precedence-and-associativity"></a>Operatorrangfolge und Assoziativität

 Die Art und Weise, wie ein Ausdruck ausgewertet wird, unterliegt den Regeln der Assoziativität und Operatorrangfolge. Weitere Informationen finden Sie unter [Operatoren](../../language-reference/operators/index.md).  
  
 Die meisten Ausdrücke, außer Zuweisungsausdrücke und Methodenaufrufausdrücke, müssen in einer Anweisung eingebettet sein. Weitere Informationen finden Sie unter [Anweisungen](./statements.md).  
  
## <a name="literals-and-simple-names"></a>Literale und einfache Namen

 Die zwei einfachsten Typen von Ausdrücken sind Literale und einfache Namen. Ein Literal ist ein konstanter Wert, der keinen Namen besitzt. Im folgenden Codebeispiel sind z.B. `5` und `"Hello World"` jeweils Literalwerte:  
  
 [!code-csharp[csProgGuideStatements#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#2)]  
  
 Weitere Informationen zu Literalen finden Sie unter [Typen](/dotnet/csharp/language-reference/keywords).  
  
 Im vorherigen Beispiel sind `i` und `s` jeweils einfache Namen, die lokale Variablen identifizieren. Wenn diese Variablen in einem Ausdruck verwendet werden, ergibt der Variablenname einen Wert, der derzeit am Speicherort der Variable im Speicher gespeichert ist. Dies wird im folgenden Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideStatements#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#3)]

## <a name="invocation-expressions"></a>Aufrufausdrücke

 Im folgenden Codebeispiel ist der Aufruf von `DoWork` ein Aufrufausdruck.  
  
```csharp
DoWork();  
```  
  
 Ein Methodenaufruf erfordert den Namen der Methode entweder als Name wie im vorherigen Beispiel oder als Ergebnis eines anderen Ausdrucks, gefolgt von einer Klammer und beliebigen Methodenparametern. Weitere Informationen finden Sie unter [Methoden](../classes-and-structs/methods.md). Ein Delegataufruf verwendet den Namen eines Delegaten sowie Methodenparameter in Klammern. Weitere Informationen finden Sie unter [Delegaten](../delegates/index.md). Methodenaufrufe und Delegataufrufe ergeben den Rückgabewert der Methode, wenn die Methode einen Wert zurückgibt. Methoden, die „void“ zurückgeben, können nicht anstatt eines Werts in einem Ausdruck verwendet werden.  

## <a name="query-expressions"></a>Abfrageausdrücke

 Die gleichen Regeln für Ausdrücke gelten allgemein für Abfrageausdrücke. Weitere Informationen finden Sie unter [LINQ](../../linq/index.md).  
  
## <a name="lambda-expressions"></a>Lambdaausdrücke

 Lambdaausdrücke stellen „Inlinemethoden“ dar, die keinen Namen haben, jedoch über Eingabeparameter und mehrere Anweisungen verfügen können. Sie werden häufig in LINQ verwendet, um Argumente Methoden zu übergeben. Lambdaausdrücke werden entweder zu Delegaten oder Ausdrucksbaumstrukturen kompiliert. Dies hängt vom Kontext ab, in dem sie verwendet werden. Weitere Informationen finden Sie unter [Lambdaausdrücke](lambda-expressions.md).  
  
## <a name="expression-trees"></a>Ausdrucksbaumstrukturen

Mithilfe von Ausdrucksbaumstrukturen können Ausdrücke als Datenstrukturen dargestellt werden. Sie werden häufig von LINQ-Anbietern verwendet, um Abfrageausdrücke in Code zu übersetzen, der in einem anderen Kontext aussagekräftig ist, z.B. als SQL-Datenbank. Weitere Informationen finden Sie unter [Ausdrucksbaumstrukturen (C#)](../concepts/expression-trees/index.md).
  
## <a name="expression-body-definitions"></a>Ausdruckstextdefinitionen

C# unterstützt *Ausdruckskörpermember*, mit denen Sie eine präzise Ausdrückskörperdefiniton für Methoden, Konstruktoren, Finalizer, Eigenschaften und Indexer angeben können. Weitere Informationen finden Sie unter [Ausdruckskörpermember](expression-bodied-members.md).

## <a name="remarks"></a>Anmerkungen

 Wann immer eine Variable, eine Objekteigenschaft oder ein Objektindexerzugriff von einem Ausdruck identifiziert wird, wird der Wert dieses Elements als Wert des Ausdrucks verwendet. Ein Ausdruck kann dort in C# platziert werden, wo ein Wert oder Objekt benötigt wird, solange der Ausdruck letztendlich den geforderten Typ ergibt.  

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Ausdrücke](~/_csharplang/spec/expressions.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Operatoren](../../language-reference/operators/index.md)
- [Methoden](../classes-and-structs/methods.md)
- [Delegaten](../delegates/index.md)
- [Typen](../types/index.md)
- [LINQ](../../linq/index.md)
