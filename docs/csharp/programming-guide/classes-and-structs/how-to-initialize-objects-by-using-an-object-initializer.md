---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: a2ecc9df211d0082bd4b413653e374758c877abc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705586"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)

Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.  
  
Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden. Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden. Daher tritt bei Objektinitialisierern, die öffentlichen Zugriff benötigen, ein Fehler auf, wenn der parameterlose Konstruktor in der Klasse als `private` deklariert wird.
  
Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren. Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt. Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen. Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen. Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Objekt- und Auflistungsinitialisierer](object-and-collection-initializers.md)
