---
title: when (C#-Referenz)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ae869fa04d2dfb963694f258624c5cd594ff1184
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
 # <a name="when-c-reference"></a>when (C#-Referenz)

Sie können das kontextabhängige Schlüsselwort `when` verwenden, um eine Filterbedingung in zwei Kontexten anzugeben:

- In der `catch`-Anweisung eines [try/catch](try-catch.md)- oder [try/catch/finally](try-catch-finally.md)-Blocks
- In der `case`-Bezeichnung einer [switch](switch.md)-Anweisung

## <a name="when-in-a-catch-statement"></a>`when` in einer `catch`-Anweisung

Ab mit C# 6 kann `When` in einer `catch`-Anweisung verwendet werden, um eine Bedingung mit dem Wert „TRUE“ für den Handler anzugeben, damit eine spezifische Ausnahme ausgeführt werden kann. Die Syntax lautet:

```csharp
catch ExceptionType [e] when (expr)
```
where *expr* ist ein Ausdruck, der einen booleschen Wert ergibt. Wenn `true` zurückgegeben wird, wird der Ausnahmehandler ausgeführt; wenn `false` zurückgegeben wird, nicht. 

Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um Handler abhängig vom Text der Ausnahmemeldung für @System.Net.HttpRequestException bedingt auszuführen.

 [!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` in einer `switch`-Anweisung

Ab mit C# 7 müssen sich `case`-Bezeichnungen nicht mehr gegenseitig ausschließen, und die Reihenfolge, in der `case`-Bezeichnungen in einer `switch`-Anweisung angezeigt werden, kann bestimmen, welcher Schalterblock ausgeführt wird. Das Schlüsselwort `when` kann verwendet werden, um eine Filterbedingung anzugeben, die dazu führt, dass die zugeordnete case-Bezeichnung nur TRUE ist, wenn die Filterbedingung ebenfalls TRUE ist. Die Syntax lautet:

```csharp
case (expr) when (when-condition):
```
Wo *expr* ein Konstantenmuster oder Typmuster ist, das mit dem match-Ausdruck verglichen wird, und wo *when-condition* ein beliebiger boolescher Ausdruck ist 

Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um auf `Shape`-Objekte zu testen, die einen Bereich von 0 haben, und um auf eine Vielzahl von `Shape`-Objekten zu testen, die einen Bereich größer als 0 aufweisen. 

 [!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Siehe auch 
  [switch-Anweisung](switch.md)  
  [Try-Catch-Anweisung](try-catch.md)  
  [try/catch/finally-Anweisung](try-catch-finally.md) 


