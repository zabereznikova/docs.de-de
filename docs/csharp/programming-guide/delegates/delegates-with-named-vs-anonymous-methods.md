---
title: Delegaten mit benannten im Vergleich zu Anonyme Methoden – C#-Programmierhandbuch
description: Lernen Sie Delegaten mit benannten im Vergleich zu anonymen Methoden kennen. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: d8d2c6d8c7792b81f2fc2e25d0836e3780e58e52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202499"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a>Delegaten mit benannten im Vergleich zu Anonyme Methoden (C#-Programmierhandbuch)

Ein [Delegat](../../language-reference/builtin-types/reference-types.md) kann einer benannten Methode zugeordnet werden. Wenn Sie einen Delegaten mit einer benannten Methode instanziieren, wird die Methode als Parameter übergeben:  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 Dies wird mit einer benannten Methode aufgerufen. Mit einer benannten Methode erstellte Delegaten können entweder eine [statische](../../language-reference/keywords/static.md) Methode oder eine Instanzmethode kapseln. Benannte Methoden sind die einzige Möglichkeit, einen Delegaten in früheren Versionen von C# zu instanziieren. Wenn das Erstellen einer neuen Methode jedoch einen unerwünschten Aufwand für Sie darstellt, können Sie in C# einen Delegaten instanziieren und sofort einen Codeblock bestimmen, den der Delegat bei seinem Aufruf verarbeitet. Der Block kann entweder einen Lambdaausdruck oder eine anonyme Methode enthalten. Weitere Informationen finden Sie unter [Anonyme Funktionen](../statements-expressions-operators/anonymous-functions.md).  
  
## <a name="remarks"></a>Hinweise  

 Die Methode, die Sie als Delegatparameter übergeben, muss die gleiche Signatur wie die Delegatdeklaration aufweisen.  
  
 Eine Delegatinstanz kann entweder eine statische Methode oder eine Instanzmethode kapseln.  
  
 Obwohl der Delegat einen [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter verwenden kann, wird empfohlen, ihn nicht mit Multicast-Ereignisdelegaten zu verwenden, da Sie nicht wissen können, welcher Delegat aufgerufen wird.  
  
## <a name="example-1"></a>Beispiel 1  

 In diesem einfachen Beispiel wird ein Delegat deklariert und verwendet. Beachten Sie, dass der Delegat `Del` und die zugeordnete Methode `MultiplyNumbers` dieselbe Signatur aufweisen.  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a>Beispiel 2  

 Im folgenden Beispiel wird ein Delegat sowohl einer statischen Methode als auch einer Instanzmethode zugeordnet und gibt von jeder spezifische Informationen zurück.  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Delegaten](./index.md)
- [Kombinieren von Delegaten (Multicastdelegaten)](./how-to-combine-delegates-multicast-delegates.md)
- [Ereignisse](../events/index.md)
