---
title: "Benannte und optionale Argumente (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "namedParameter_CSharpKeyword"
  - "cs_namedParameter"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Argumente [C#], Benannt"
  - "Argumente [C#], Optional"
  - "Benannte und optionale Argumente [C#]"
  - "Benannte Argumente [C#]"
  - "Optionale Argumente [C#]"
  - "Parameter [C#], Benannt"
  - "Parameter [C#], Optional"
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 43
---
# Benannte und optionale Argumente (C#-Programmierhandbuch)
[!INCLUDE[csharp_dev10_long](../../../csharp/programming-guide/classes-and-structs/includes/csharp-dev10-long-md.md)] stellt erstmals benannte und optionale Argumente bereit.  *Benannte Argumente* ermöglichen Ihnen, ein Argument für einen bestimmten Parameter anzugeben, indem Sie das Argument dem Parameternamen statt der Position des Parameters in der Parameterliste zuordnen.  *Optionale Argumente* ermöglichen Ihnen, Argumente für einige Parameter wegzulassen.  Beide Techniken können mit Methoden, Indexern, Konstruktoren und Delegaten verwendet werden.  
  
 Bei der Verwendung von benannten und optionalen Argumenten werden die Argumente in der Reihenfolge ausgewertet, die die Argumentliste vorgibt, nicht die Parameterliste.  
  
 Wenn Sie benannte und optionale Argumente zusammen verwenden, haben Sie die Möglichkeit, Argumente für nur einige Parameter aus einer Liste mit optionalen Parametern anzugeben.  Durch diese Funktion werden Aufrufe von COM\-Schnittstellen, wie z. B. Microsoft Office\-Automatisierungs\-APIs, enorm vereinfacht.  
  
## Benannte Argumente  
 Wenn Sie benannte Argumente nutzen, müssen Sie sich nicht mehr um die Reihenfolge der Parameter in den Parameterlisten aufgerufener Methoden kümmern.  Sie können die Parameter für die einzelnen Argumente anhand des Parameternamens angeben.  Beispiel: Eine Funktion zur Berechnung des Body\-Mass\-Index \(BMI\) kann mit dem Standardverfahren aufgerufen werden, indem die Argumente für Gewicht und Größe nach Position in der von der Funktion definierten Reihenfolge gesendet werden.  
  
 `CalculateBMI(123, 64);`  
  
 Wenn Sie sich nicht an die Reihenfolge der Parameter, wohl aber an ihre Namen erinnern, können Sie die Argumente in beliebiger Reihenfolge senden \(Gewicht zuerst oder Größe zuerst\).  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 Durch benannte Argumente wird außerdem die Lesbarkeit des Codes verbessert, indem identifiziert wird, welchen Wert die einzelnen Argumente darstellen.  
  
 Ein benanntes Argument kann auf Positionsargumente folgen, wie hier gezeigt.  
  
 `CalculateBMI(123, height: 64);`  
  
 Ein Positionsargument kann jedoch nicht auf ein benanntes Argument folgen.  Die folgende Anweisung verursacht einen Compilerfehler.  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## Beispiel  
 Mit dem folgenden Code werden die Beispiele aus diesem Abschnitt implementiert.  
  
 [!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/program.cs#1)]  
  
## Optionale Argumente  
 In der Definition einer Methode, eines Konstruktors, eines Indexers oder eines Delegaten kann angegeben sein, ob die Parameter erforderlich oder optional sind.  Bei jedem Aufruf müssen Argumente für alle erforderlichen Parameter bereitgestellt werden, Argumente für optionale Parameter können jedoch weggelassen werden.  
  
 Ein Standardwert ist Teil der Definition jedes optionalen Parameters.  Dieser Standardwert wird verwendet, wenn für einen Parameter kein Argument gesendet wird.  Der Standardwert muss einen der folgenden Typen von Ausdrücken sein:  
  
-   ein konstanter Ausdruck.  
  
-   Ein Ausdruck der Form `new ValType()`, in dem `ValType` ein Werttyp ist, z. B. [Enumeration](../../../csharp/language-reference/keywords/enum.md) oder [Struktur](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
-   Ein Ausdruck der Form [ValType \(Standard\)](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md), in dem `ValType` ein Werttyp ist.  
  
 Optionale Parameter werden am Ende der Parameterliste nach den erforderlichen Parametern definiert.  Wenn der Aufrufer ein Argument für einen Parameter in einer Folge von optionalen Parametern bereitstellt, müssen auch Argumente für alle vorangehenden optionalen Parameter bereitgestellt werden.  Durch Trennzeichen getrennte Lücken in der Argumentliste werden nicht unterstützt.  Im folgenden Code z. B. ist die `ExampleMethod`\-Instanzmethode durch einen erforderlichen und zwei optionale Parameter definiert.  
  
 [!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/optional.cs#15)]  
  
 Der folgende Aufruf von `ExampleMethod` verursacht einen Compilerfehler, da ein Argument zwar für den dritten, aber nicht für den zweiten Parameter bereitgestellt wird.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Wenn Sie jedoch den Namen des dritten Parameters kennen, können Sie die Aufgabe mithilfe eines benannten Arguments lösen.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 IntelliSense zeigt optionale Parameter in Klammern an, wie in der folgenden Abbildung dargestellt.  
  
 ![IntelliSense&#45;QuickInfo für ExampleMethod&#45;Methode.](../../../csharp/programming-guide/classes-and-structs/media/optional-parameters.png "Optional\_Parameters")  
Optionale Parameter in ExampleMethod  
  
> [!NOTE]
>  Sie können optionale Parameter auch mit der .NET\-Klasse <xref:System.Runtime.InteropServices.OptionalAttribute> deklarieren.  `OptionalAttribute`\-Parameter erfordern keinen Standardwert.  
  
## Beispiel  
 Der Konstruktor für `ExampleClass` im folgenden Beispiel weist einen Parameter auf, der optional ist.  Die Instanzmethode `ExampleMethod` weist einen erforderlichen Parameter \(`required`\) und zwei optionale Parameter \(`optionalstr` und `optionalint`\) auf.  Der Code in `Main` veranschaulicht die unterschiedlichen Methoden, mit denen der Konstruktor und die Methode aufgerufen werden können.  
  
 [!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/optional.cs#2)]  
  
## COM\-Schnittstellen  
 Benannte und optionale Argumente sorgen wie auch die Unterstützung für dynamische Objekte und andere Erweiterungen für eine erhebliche Verbesserung der Interoperabilität mit COM\-APIs, wie z. B. Office\-Automatisierungs\-APIs.  
  
 Beispiel: Die [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201)\-Methode in der Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196)\-Schnittstelle verfügt über sieben Parameter, die alle optional sind.  Diese Parameter sind in der folgenden Abbildung enthalten.  
  
 ![IntelliSense&#45;QuickInfo für die AutoFormat&#45;Methode.](../../../csharp/programming-guide/classes-and-structs/media/autoformat-parameters.png "AutoFormat\_Parameters")  
AutoFormat\-Parameter  
  
 In C\# 3.0 und früheren Versionen ist ein Argument für jeden Parameter erforderlich, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/namedandoptcom.cs#3)]  
  
 Sie können den Aufruf von `AutoFormat` jedoch sehr vereinfachen, indem Sie benannte und optionale Argumente verwenden, die in C\# 4.0 eingeführt wurden.  Benannte und optionale Argumente ermöglichen Ihnen, das Argument für einen optionalen Parameter wegzulassen, wenn Sie den Standardwert des Parameters nicht ändern möchten.  Im folgenden Aufruf wird für nur einen der sieben Parameter ein Wert angegeben.  
  
 [!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/namedandoptionalsnippets/namedandoptcom.cs#13)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office\-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) und [Gewusst wie: Zugreifen auf Office\-Interop\-Objekte mithilfe von Visual C\#\-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
## Überladungsauflösung  
 Die Verwendung von benannten und optionalen Argumenten wirkt sich wie folgt auf die Überladungsauflösung aus:  
  
-   Eine Methode, ein Indexer oder ein Konstruktor kommt für die Ausführung in Frage, wenn jeder der zugehörigen Parameter entweder optional ist oder anhand von Name oder Position einem einzelnen Argument in der aufrufenden Anweisung zugewiesen ist, das in den Typ des Parameters konvertiert werden kann.  
  
-   Bei mehreren möglichen Kandidaten werden die Überladungsauflösungsregeln für bevorzugte Konvertierungen auf die explizit angegebenen Argumente angewendet.  Weggelassene Argumente für optionale Parameter werden ignoriert.  
  
-   Wenn zwei Kandidaten gleich gut geeignet sind, wird der Kandidat bevorzugt, der keine optionalen Parameter aufweist, für die Argumente weggelassen wurden.  Die Ursache hierfür ist eine allgemeine Einstellung für die Überladungsauflösung für Kandidaten mit weniger Parametern.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [Gewusst wie: Verwenden von benannten und optionalen Argumenten in der Office\-Programmierung](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)   
 [Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md)