---
title: Benannte und optionale Argumente (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e6fceb569a79b5988171f06ae6c09d86b5fc667d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Benannte und optionale Argumente (C#-Programmierhandbuch)
[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] führt benannte und optionale Argumente ein. *Benannte Argumente* ermöglichen es Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen anstatt der Position des Parameters in der Parameterliste zuordnen. *Optionale Argumente* ermöglichen es Ihnen, Argumente für einige Parameter auszulassen. Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.  
  
 Wenn Sie benannte und optionale Argumente verwenden, werden die Argumente in der Reihenfolge ausgewertet, in der sie in der Argumentliste, nicht in der Parameterliste, erscheinen.  
  
 Wenn Sie benannte und optionale Parameter zusammen verwenden, können Sie Argumente für nur ein paar Parameter aus einer Liste von optionalen Parametern bereitstellen. Diese Funktion erleichtert den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office erheblich.  
  
## <a name="named-arguments"></a>Benannte Argumente  
 Bei Verwendung benannter Argumente bleibt es Ihnen erspart, sich an die Reihenfolge von Parametern in den Parameterlisten von aufgerufenen Methoden zu erinnern oder sie nachzuschauen. Der Parameter für jedes Argument kann vom Parameternamen angegeben werden. Z. B. eine Funktion, die Bestelldetails ausgibt (z. B. Verkäufer Name, Order Anzahl & Product Name) kann auf die übliche Weise aufgerufen werden, durch das Senden von Argumenten nach Position in der Reihenfolge von der Funktion definiert.
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 Wenn Sie sich nicht auf die Reihenfolge der Parameter erinnern, aber ihre Namen kennen, können Sie die Argumente in beliebiger Reihenfolge senden.  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 Benannte Argumente verbessern auch die Lesbarkeit des Codes, indem sie identifizieren, was jedes Argument darstellt. In der folgenden Beispielmethode der `sellerName` darf nicht Null oder leer sein. Beide `sellerName` und `productName` sind Zeichenfolgentypen, anstatt das Senden von Argumenten nach Position, ist es sinnvoll, benannte Argumente verwenden, um die beiden eindeutig und weniger Verwirrung für jede Person beim Lesen des Codes.
  
 Benannte Argumente, bei der Verwendung mit Positionsargumenten, gelten als 

- Sie sind keine Positionsargumente gefolgt oder

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- _beginnend mit c# 7.2_, sie sind in der richtigen Position verwendet. Im folgenden Beispiel ist der Parameter `orderNum` befindet sich in der richtigen Position aber wird nicht explizit benannt.

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 Benannte Argumente außerhalb der normalen Reihenfolge sind jedoch ungültig, wenn sie von positionellen Argumenten befolgt werden.

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert die Beispielen in diesem Abschnitt sowie einige zusätzlichen Spalten.  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a>Optionale Argumente  
 Die Definition einer Methode, eines Konstruktors, eines Indexers oder Delegaten kann angeben, dass deren Parameter benötigt werden oder optional sind. Jeder Aufruf muss Argumente für alle benötigten Parameter bereitstellen, kann aber Argumente für optionale Parameter auslassen.  
  
 Jeder optionale Parameter hat einen Standardwert als Teil seiner Definition. Wenn für diesen Parameter kein Argument gesendet wird, wird der Standardwert verwendet. Ein Standardwert muss einer der folgenden Typen von Ausdrücken sein:  
  
-   Ein konstanter Ausdruck  
  
-   Ein Ausdruck der Form `new ValType()`, wobei `ValType` ein Werttyp wie [enum](../../../csharp/language-reference/keywords/enum.md) oder [struct](../../../csharp/programming-guide/classes-and-structs/structs.md) ist  
  
-   Ein Ausdruck in Form von [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), wobei `ValType` ein Werttyp ist  
  
 Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert. Wenn der Aufrufer ein Argument für einen beliebigen Parameter aus einer Folge von optionalen Parametern bereitstellt, muss er Argumente für alle vorherigen optionalen Parameter bereitstellen. Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt. Im folgenden Code wird z.B. die Instanzmethode `ExampleMethod` mit einem erforderlichen und zwei optionalen Parametern definiert.  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument für den dritten Parameter, aber nicht für den zweiten, bereitgestellt wird.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Wenn Sie den Namen des dritten Parameters kennen, können Sie ein benanntes Argument zum Ausführen der Aufgabe verwenden.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 IntelliSense verwendet zum Anzeigen von optionalen Parametern Klammern, wie in folgender Abbildung veranschaulicht wird.  
  
 ![IntelliSense-QuickInfo für die Methode „ExampleMethod.“](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")  
Optionale Parameter in ExampleMethod  
  
> [!NOTE]
>  Sie können auch optionale Parameter mit der .NET-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren. `OptionalAttribute`-Parameter erfordern keinen Standardwert.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel hat der Konstruktor für `ExampleClass` einen Parameter, der optional ist. Instanzmethode `ExampleMethod` hat einen erforderlichen Parameter (`required`) und zwei optionale Parameter (`optionalstr` und `optionalint`). Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, in denen der Konstruktor und die Methode aufgerufen werden können.  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a>COM-Schnittstellen  
 Benannte und optionale Argumente verbessern zusammen mit der Unterstützung von dynamischen Objekten und anderen Verbesserungen deutlich die Interoperabilität mit COM-APIs wie Office-Automatisierungs-APIs.  
  
 Die Methode [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) hat z.B. in der Schnittstelle [Bereich](http://go.microsoft.com/fwlink/?LinkId=148196) von Microsoft Office Excel sieben Parameter, von denen alle optional sind. Diese Parameter sind in der folgenden Abbildung dargestellt.  
  
 ![IntelliSense-QuickInfo für die AutoFormat-Methode.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")  
AutoFormat-Parameter  
  
 In C# 3.0 und früheren Versionen wird ein Argument für jeden Parameter benötigt, wie im folgenden Beispiel gezeigt wird.  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 Sie können jedoch den Aufruf an `AutoFormat` erheblich vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C# 4.0 eingeführt wurden. Benannte und optionale Parameter helfen Ihnen dabei, das Argument für einen optionalen Parameter auszulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten. Im folgenden Aufruf wird ein Wert für nur einen der sieben Parameter angegeben.  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Vorgehensweise: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) und [Vorgehensweise: Zugreifen auf Office Interop-Objekte mithilfe von Visual C#-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
## <a name="overload-resolution"></a>Overload Resolution  
 Das Verwenden von benannten und optionalen Argumenten wirkt sich auf die Überladungsauflösung folgendermaßen aus:  
  
-   Eine Methode, ein Indexer oder ein Konstruktor ist ein Kandidat für die Ausführung, wenn jeder der Parameter entweder optional ist oder über Namen oder Position auf ein einzelnes Argument in der aufrufenden Anweisung reagiert. Dieses Argument kann in dem Typ des Parameters konvertiert werden.  
  
-   Wenn mehr als ein Kandidat gefunden wird, werden die Regeln der Überladungsauflösung als bevorzugte Konvertierungen auf die Argumente angewandt, die ausdrücklich angegeben sind. Ausgelassene Argumente für optionale Parameter werden ignoriert.  
  
-   Wenn zwei Kandidaten gleich gut geeignet sind, wird ein Kandidat bevorzugt, der keine optionalen Parameter besitzt, für die Argumente im Aufruf ausgelassen wurden. Dies ist die Folge einer allgemeinen Präferenz bei der Überladungsauflösung für Kandidaten, die weniger Parameter besitzen.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md)
