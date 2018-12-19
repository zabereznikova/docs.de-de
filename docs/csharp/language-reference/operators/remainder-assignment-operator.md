---
title: '%=-Operator – C#-Referenz'
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: d0732f9578b64c894ecc1d3bb15cee11a8d5b6a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245560"
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
  
Der [Restoperator](remainder-operator.md) `%` berechnet den Rest nach der Division seiner Operanden. Er wird von allen numerischen Typen unterstützt.

Wenn ein benutzerdefinierter Typ den [Restoperator](remainder-operator.md) `%` [überlädt](../keywords/operator.md), ist der Restzuweisungsoperator `%=` implizit überladen.
  
Im folgenden Beispiel wird die Verwendung des `%=`-Operators veranschaulicht:

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
