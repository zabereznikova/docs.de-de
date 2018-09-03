---
title: Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 9986a91b18c536773f4ca20b71c54588c3e95f32
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43476130"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)
Mit Objektinitialisierern können Sie allen verfügbaren Feldern oder Eigenschaften eines Objekts zum Erstellungszeitpunkt Werte zuweisen, ohne einen Konstruktor gefolgt von Zeilen mit Zuweisungsanweisungen aufrufen zu müssen. Mit der Objektinitialisierersyntax können Sie Argumente für einen Konstruktor angeben oder die Argumente (und Klammersyntax) weglassen.  Im folgenden Beispiel werden die Verwendung eines Objektinitialisierers mit einem benannten Typ, `Cat`, und das Aufrufen des Standardkonstruktors veranschaulicht. Beachten Sie die Verwendung automatisch implementierter Eigenschaften in der `Cat`-Klasse. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
Die Syntax von Objektinitialisierern ermöglicht Ihnen die Erstellung einer Instanz und weist danach das neu erstellte Objekt mit seinen zugewiesenen Eigenschaften der Variable in der Zuweisung zu.
  
## <a name="object-initializers-with-anonymous-types"></a>Objektinitialisierer mit anonymen Typen  
 Obwohl Objektinitialisierer in jedem Kontext verwendet werden können, sind sie vor allem in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücken nützlich. Abfrageausdrücke verwenden häufig [anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), die nur mit einem Objektinitialisierer initialisiert werden können, wie in der folgenden Deklaration veranschaulicht.  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 Anonyme Typen ermöglichen der `select`-Klausel in einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck, Objekte der ursprünglichen Sequenz in Objekte zu transformieren, deren Wert und Form sich vom Original unterscheiden können. Dies ist nützlich, wenn Sie nur einen Teil der Informationen aus jedem Objekt in einer Sequenz speichern möchten. Im folgenden Beispiel wird angenommen, dass ein Produktobjekt (`p`) viele Felder und Methoden enthält und dass Sie nur eine Sequenz von Objekten erstellen möchten, die den Produktnamen und den Einzelpreis enthalten.  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 Wenn diese Abfrage ausgeführt wird, enthält die `productInfos`-Variable eine Sequenz von Objekten, auf die Sie über eine `foreach`-Anweisung, wie im folgenden Beispiel gezeigt, zugreifen können:  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 Jedes Objekt im neuen anonymen Typ hat zwei öffentliche Eigenschaften, die die gleichen Namen wie die Eigenschaften oder Felder im ursprünglichen Objekt erhalten. Sie können ein Feld auch umbenennen, wenn Sie einen anonymen Typ erstellen. Im folgenden Beispiel wird das `UnitPrice`-Feld in `Price` umbenannt.  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="collection-initializers"></a>Auflistungsinitialisierer  
 Mit Auflistungsinitialisierern können Sie einen oder mehrere Elementinitialisierer festlegen, wenn Sie einen Auflistungstyp initialisieren, der <xref:System.Collections.IEnumerable> implementiert und über `Add` mit der entsprechenden Signatur als Instanzmethode oder Erweiterungsmethode verfügt. Die Elementinitialisierer können ein einfacher Wert, ein Ausdruck oder ein Objektinitialisierer sein. Durch den Einsatz eines Auflistungsinitialisierers müssen Sie nicht mehrere Aufrufe der `Add`-Methode für die Klasse in Ihrem Quellcode angeben; der Compiler fügt die Aufrufe hinzu.  
  
 In den folgenden Beispielen werden zwei einfache Auflistungsinitialisierer dargestellt:  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 Der folgende Auflistungsinitialisierer verwendet Objektinitialisierer, um Objekte der `Cat`-Klasse, die in einem vorherigen Beispiel definiert wurden, zu initialisieren. Beachten Sie, dass die einzelnen Objektinitialisierer in geschweifte Klammern eingeschlossen und durch Kommas voneinander getrennt werden.  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 Sie können [NULL](../../../csharp/language-reference/keywords/null.md) als ein Element in einem Auflistungsinitialisierer festlegen, wenn die `Add`-Methode der Auflistung dies zulässt.  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 Sie können indizierte Elemente angeben, falls die Auflistung  die Indizierung unterstützt.  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a>Beispiele

 Im folgenden Beispiel werden die Konzepte des Objekt- und Auflistungsinitialisierers verbunden.

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 Wie im folgenden Beispiel gezeigt wird, ermöglicht ein Objekt, das <xref:System.Collections.IEnumerable> mit einer `Add`-Methode mit mehreren Parametern implementiert, Auflistungsinitialisierer mit mehreren Elementen pro Element in der Liste, die der Signatur der `Add`-Methode entsprechen. 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 `Add`-Methoden können durch das Schlüsselwort `params` eine variable Anzahl von Argumenten akzeptieren, wie im folgenden Beispiel gezeigt wird. Dieses Beispiel zeigt die benutzerdefinierte Implementierung eines Indexers sowie die Initialisierung einer Auflistung mithilfe von Indizes.
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
