---
title: 'Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie Objektinitialisierer verwenden, um Typobjekte in C# zu initialisieren, ohne einen Konstruktor aufzurufen. Verwenden Sie einen Objektinitialisierer, um einen anonymen Typ zu definieren.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 97f537a8361c612580cc9bb41cef327e310287c2
ms.sourcegitcommit: d66641bc7c14ad7d02300316e9e7e84a875a0a72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2020
ms.locfileid: "91712664"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Gewusst wie: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)

Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.  
  
Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden. Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den parameterlosen Instanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden. Daher tritt bei Objektinitialisierern, die öffentlichen Zugriff benötigen, ein Fehler auf, wenn der parameterlose Konstruktor in der Klasse als `private` deklariert wird.
  
Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren. Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt. Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen. Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen. Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Objekt- und Auflistungsinitialisierer](object-and-collection-initializers.md)
