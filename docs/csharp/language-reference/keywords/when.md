---
title: when – C#-Referenz
ms.custom: seodec18
ms.date: 03/07/2017
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
ms.openlocfilehash: 103309b5e5a121647576ce120f4353b4ceef08c4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235526"
---
 # <a name="when-c-reference"></a>when (C#-Referenz)

Sie können das kontextabhängige Schlüsselwort `when` verwenden, um eine Filterbedingung in zwei Kontexten anzugeben:

- In der `catch`-Anweisung eines [try/catch](try-catch.md)- oder [try/catch/finally](try-catch-finally.md)-Blocks
- In der `case`-Bezeichnung einer [switch](switch.md)-Anweisung

## <a name="when-in-a-catch-statement"></a>`when` in einer `catch`-Anweisung

Ab mit C# 6 kann `when` in einer `catch`-Anweisung verwendet werden, um eine Bedingung mit dem Wert „TRUE“ für den Handler anzugeben, damit eine spezifische Ausnahme ausgeführt werden kann. Die Syntax lautet:

```csharp
catch (ExceptionType [e]) when (expr)
```
where *expr* ist ein Ausdruck, der einen booleschen Wert ergibt. Wenn `true` zurückgegeben wird, wird der Ausnahmehandler ausgeführt; wenn `false` zurückgegeben wird, nicht. 

Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um Handler abhängig vom Text der Ausnahmemeldung für <xref:System.Net.Http.HttpRequestException> bedingt auszuführen.

 [!code-csharp[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a>`when` in einer `switch`-Anweisung

Ab C# 7.0 müssen sich `case`-Bezeichnungen nicht mehr gegenseitig ausschließen, und die Reihenfolge, in der `case`-Bezeichnungen in einer `switch`-Anweisung angezeigt werden, kann bestimmen, welcher Schalterblock ausgeführt wird. Das Schlüsselwort `when` kann verwendet werden, um eine Filterbedingung anzugeben, die dazu führt, dass die zugeordnete case-Bezeichnung nur TRUE ist, wenn die Filterbedingung ebenfalls TRUE ist. Die Syntax lautet:

```csharp
case (expr) when (when-condition):
```
Wo *expr* ein Konstantenmuster oder Typmuster ist, das mit dem match-Ausdruck verglichen wird, und wo *when-condition* ein beliebiger boolescher Ausdruck ist 

Im folgenden Beispiel wird das Schlüsselwort `when` verwendet, um auf `Shape`-Objekte zu testen, die einen Bereich von 0 haben, und um auf eine Vielzahl von `Shape`-Objekten zu testen, die einen Bereich größer als 0 aufweisen. 

 [!code-csharp[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a>Siehe auch

- [switch-Anweisung](switch.md)  
- [Try-Catch-Anweisung](try-catch.md)  
- [try/catch/finally-Anweisung](try-catch-finally.md) 
