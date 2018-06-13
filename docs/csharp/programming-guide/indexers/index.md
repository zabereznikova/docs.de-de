---
title: Indexer (C#-Programmierhandbuch)
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: acc82ca370a71a0469fc543d042da9c279d69fb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334219"
---
# <a name="indexers-c-programming-guide"></a>Indexer (C#-Programmierhandbuch)

Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden. Der indizierte Wert kann festgelegt oder ohne explizite Angabe eines Typs oder Instanzmembers abgerufen werden. Indexer ähneln [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Zugriffsmethoden Parameter verwenden.  
 
 Im folgenden Beispiel wird eine generische Klasse mit einfachen [get](../../../csharp/language-reference/keywords/get.md)- und [set](../../../csharp/language-reference/keywords/set.md)-Accessormethoden zum Zuweisen und Abrufen von Werten definiert. Die `Program`-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  Weitere Beispiele finden Sie unter [Verwandte Abschnitte](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Ausdruckstextdefinitionen  
 
Get- oder Set-Accessoren eines Indexers bestehen häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt oder festlegt. Ausdruckskörpermember bieten eine vereinfachte Syntax zur Unterstützung dieses Szenarios. Ab C# 6 kann ein schreibgeschützter Indexer als Ausdruckskörpermember implementiert werden, wie im folgenden Beispiel gezeigt.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Beachten Sie, dass `=>` den Ausdruckstext vorstellt und dass das `get`-Schlüsselwort nicht verwendet wird. 

Ab C# 7.0 können die Get- und die Set-Zugriffsmethode als Ausdruckskörpermember implementiert werden. In diesem Fall müssen die Schlüsselwörter `get` und `set` verwendet werden. Zum Beispiel:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Übersicht über Indexer  
  
-   Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.  
  
-   Ein `get`-Accessor gibt einen Wert zurück. Ein `set`-Accessor weist einen Wert zu.  
  
-   Das [this](../../../csharp/language-reference/keywords/this.md)-Schlüsselwort wird zum Definieren des Indexers verwendet.  
  
-   Das [value](../../../csharp/language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Indexer zugewiesen wird.  
  
-   Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.  
  
-   Indexer können überladen werden.  
  
-   Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D-Array.  
  
##  <a name="BKMK_RelatedSections"></a> Verwandte Abschnitte  
  
-   [Verwenden von Indexern](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Indexer in Schnittstellen](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Vergleich zwischen Eigenschaften und Indexern](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Einschränken des Zugriffsmethodenzugriffs](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
