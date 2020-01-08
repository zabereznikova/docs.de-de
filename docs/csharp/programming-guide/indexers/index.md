---
title: Indexer – C#-Programmierhandbuch
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: c00f506a682ec5d9805537b80159fd41d2174b67
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75702947"
---
# <a name="indexers-c-programming-guide"></a>Indexer (C#-Programmierhandbuch)

Indexer ermöglichen, dass Instanzen einer Klasse oder Struktur wie Arrays indiziert werden. Der indizierte Wert kann festgelegt oder ohne explizite Angabe eines Typs oder Instanzmembers abgerufen werden. Indexer ähneln [Eigenschaften](../classes-and-structs/properties.md). Der Unterschied besteht jedoch darin, dass ihre Zugriffsmethoden Parameter verwenden.  

 Im folgenden Beispiel wird eine generische Klasse mit einfachen [get](../../language-reference/keywords/get.md)- und [set](../../language-reference/keywords/set.md)-Accessormethoden zum Zuweisen und Abrufen von Werten definiert. Die `Program`-Klasse erstellt eine Instanz dieser Klasse für das Speichern von Zeichenfolgen.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> Weitere Beispiele finden Sie unter [Verwandte Abschnitte](./index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Ausdruckstextdefinitionen  
 
Get- oder Set-Accessoren eines Indexers bestehen häufig aus einer einzelnen Anweisung, die einen Wert zurückgibt oder festlegt. Ausdruckskörpermember bieten eine vereinfachte Syntax zur Unterstützung dieses Szenarios. Ab C# 6 kann ein schreibgeschützter Indexer als Ausdruckskörpermember implementiert werden, wie im folgenden Beispiel gezeigt.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Beachten Sie, dass `=>` den Ausdruckstext vorstellt und dass das `get`-Schlüsselwort nicht verwendet wird. 

Ab C# 7.0 können die Get- und die Set-Zugriffsmethode als Ausdruckskörpermember implementiert werden. In diesem Fall müssen die Schlüsselwörter `get` und `set` verwendet werden. Zum Beispiel:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Übersicht über Indexer  
  
- Indexer ermöglichen es Objekten, in ähnlicher Weise wie Arrays indiziert zu werden.  
  
- Ein `get`-Accessor gibt einen Wert zurück. Ein `set`-Accessor weist einen Wert zu.  
  
- Das [this](../../language-reference/keywords/this.md)-Schlüsselwort wird zum Definieren des Indexers verwendet.  
  
- Das [value](../../language-reference/keywords/value.md)-Schlüsselwort wird verwendet, um den Wert zu definieren, der vom `set`-Indexer zugewiesen wird.  
  
- Indexer müssen nicht durch einen Ganzzahlwert indiziert werden. Sie können entscheiden, wie Sie den spezifischen Suchmechanismus definieren möchten.  
  
- Indexer können überladen werden.  
  
- Indexer können mehr als einen formalen Parameter aufweisen, beispielsweise beim Zugreifen auf ein 2D-Array.  
  
## <a name="BKMK_RelatedSections"></a> Verwandte Abschnitte  
  
- [Verwenden von Indexern](./using-indexers.md)  
  
- [Indexer in Schnittstellen](./indexers-in-interfaces.md)  
  
- [Vergleich zwischen Eigenschaften und Indexern](./comparison-between-properties-and-indexers.md)  
  
- [Einschränken des Zugriffsmethodenzugriffs](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie unter [Indexer](~/_csharplang/spec/classes.md#indexers) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](../classes-and-structs/properties.md)
