---
title: "Operator ^ (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4ccd32ea8abd8ca3252380083eafecad2b572ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Operator ^ (C#-Referenz)
Binäre `^`-Operatoren sind für integrale Typen und `bool` vordefiniert. Für integrale Typen berechnet `^` die bitweise XOR-Operation der Operanden. Für `bool`-Operanden berechnet `^` den XOR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn einer und nur einer der Operanden `true` ist.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `^` überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 Die Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel führt einen bitweisen XOR-Operator der folgenden beiden binären Werte aus, die den Hexadezimalwerten F8 und 3F entsprechen:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 Das Ergebnis von XOR ist `1100 0111`, was hexadezimal C7 ist.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
