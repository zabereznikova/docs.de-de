---
title: 'Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Delegaten kombinieren, um Multicastdelegaten zu erstellen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 3e86c8ed4b7b091ee8c75930d427c22aa5bc0c52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185950"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)

Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten. Eine nützliche Eigenschaft von [delegate](../../language-reference/builtin-types/reference-types.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können. Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten. Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf. Es können nur Delegaten desselben Typs kombiniert werden.  
  
 Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.  
  
## <a name="example"></a>Beispiel  

 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.MulticastDelegate>
- [C#-Programmierhandbuch](../index.md)
- [Ereignisse](../events/index.md)
