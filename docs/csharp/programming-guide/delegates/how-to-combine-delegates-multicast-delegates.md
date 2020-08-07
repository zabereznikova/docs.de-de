---
title: 'Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Delegaten kombinieren, um Multicastdelegaten zu erstellen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302736"
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
