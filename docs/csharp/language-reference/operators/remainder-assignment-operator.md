---
title: Operator %= (C#-Referenz)
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085639"
---
# <a name="-operator-c-reference"></a>Operator %= (C#-Referenz)

Der Restzuweisungsoperator

Ein Ausdruck mit dem Operator `%=`, z.B.  

```csharp
x %= y
```  

für die folgende Syntax:  

```csharp
x = x % y
```  

außer dass `x` nur einmal überprüft wird.
  
Der [Restoperator](remainder-operator.md) `%` wird von allen numerischen Typen unterstützt und berechnet den Rest nach der Division der Operanden.

Wenn ein benutzerdefinierter Typ den [Restoperator](remainder-operator.md) `%` [überlädt](../keywords/operator.md), ist der Restzuweisungsoperator `%=` implizit überladen.
  
Im folgenden Beispiel wird die Verwendung des `%=`-Operators veranschaulicht:

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
