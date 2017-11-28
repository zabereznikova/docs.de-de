---
title: "C#-Funktionen mit LINQ-Unterstützung"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2f5accb188e54e0d3e2b941832637ec33afc26b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="c-features-that-support-linq"></a>C#-Funktionen mit LINQ-Unterstützung
Im folgenden Abschnitt werden neue Sprachkonstrukte, die in C# 3.0 eingeführt werden, vorgestellt. Obwohl diese neuen Funktionen zu einem gewissen Grad mit [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen verwendet werden, sind sie nicht beschränkt auf [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] und können in jedem Kontext, in dem Sie sie nützlich finden, verwendet werden.  
  
## <a name="query-expressions"></a>Abfrageausdrücke  
 Abfrageausdrücke verwenden eine deklarative Syntax wie SQL oder XQuery, um eine Abfrage über IEnumerable-Sammlungen zu erstellen. Zur Kompilierzeit wird die Abfragesyntax in Methodenaufrufe an eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Implementierung des Anbieters der Erweiterungsmethode des Standardabfrageoperators kompiliert. Applikationen steuern die Standardabfrageoperatoren, die sich durch Angabe des entsprechenden Namespace mit einer `using`-Anweisung innerhalb des Bereichs befinden. Der folgende Abfrageausdruck nimmt ein Array von Zeichenfolgen, gruppiert sie nach dem ersten Zeichen in der Zeichenfolge und sortiert die Gruppen.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Weitere Informationen finden Sie unter [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## <a name="implicitly-typed-variables-var"></a>Implizit typisierte Variablen (var)  
 Anstatt beim Deklarieren und Initialisieren einer Variablen einen Typ explizit anzugeben, können Sie den [var](../../../../csharp/language-reference/keywords/var.md)-Modifizierer verwenden, um den Compiler zum Ableiten und Zuweisen des Typs anzuweisen, wie hier gezeigt:  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Variablen, die als `var` deklariert werden, sind ebenso stark typisiert wie Variablen, deren Typ Sie explizit angeben. Die Verwendung von `var` macht es möglich, anonyme Typen zu erstellen, aber es kann für jede lokale Variable verwendet werden. Arrays können auch mit impliziter Typisierung deklariert werden.  
  
 Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## <a name="object-and-collection-initializers"></a>Objekt- und Auflistungsinitialisierer  
 Objekt- und Auflistungsinitialisierer ermöglichen das Initialisieren von Objekten ohne expliziten Aufruf eines Konstruktors für das Objekt. Initialisierer werden in der Regel in Abfrageausdrücken verwendet, wenn sie die Quelldaten in einen neuen Datentyp projizieren. In einer Klasse namens `Customer` mit öffentlichen `Name`- und `Phone`-Eigenschaften können Objektinitialisierer wie im folgenden Code verwendet werden:  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="anonymous-types"></a>Anonyme Typen  
 Ein anonymer Typ wird vom Compiler erstellt, und der Typname ist nur für den Compiler verfügbar. Anonyme Typen stellen eine bequeme Möglichkeit zum vorübergehenden Gruppieren einer Reihe von Eigenschaften in einem Abfrageergebnis bereit, ohne einen separaten benannten Typ definieren zu müssen. Anonyme Typen werden mit einem neuen Ausdruck und einem Objektinitialisierer initialisiert, wie hier gezeigt:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Weitere Informationen finden Sie unter [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="extension-methods"></a>Erweiterungsmethoden  
 Eine Erweiterungsmethode ist eine statische Methode, die einem Typ zugeordnet werden kann, sodass sie aufgerufen werden kann, als ob es sich um eine Instanzmethode für den Typ handeln würde. Diese Funktion ermöglicht es Ihnen, neue Methoden zu vorhandenen Typen „hinzuzufügen“, ohne sie tatsächlich zu ändern. Die Standardabfrageoperatoren sind eine Reihe von Erweiterungsmethoden, die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragefunktionen für jeden Typ bieten, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  
 Ein Lambdaausdruck ist eine Inlinefunktion, die den Operator => verwendet, um Eingabeparameter vom Funktionstext zu trennen, und die zur Kompilierzeit in einen Delegaten oder eine Ausdrucksbaumstruktur konvertiert werden kann. In der [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Programmierung erhalten Sie Lambdaausdrücke, wenn Sie direkte Methodenaufrufe für die Standardabfrageoperatoren vornehmen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Anonyme Funktionen](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Lambda-Ausdrücke](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Ausdrucksbaumstrukturen (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a>Automatisch implementierte Eigenschaften  
 Automatisch implementierte Eigenschaften machen die Eigenschaftendeklaration präziser. Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, wird der Compiler ein privates, anonymes Unterstützungsfeld erstellen, auf das nur durch die Getter und Setter der Eigenschaft zugegriffen werden kann.  
  
```  
public string Name {get; set;}  
```  
  
 Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (Sprachintegrierte Abfrage (LINQ))](../../../../csharp/programming-guide/concepts/linq/index.md)
