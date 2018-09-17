---
title: FALSE-Operator (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- false operator keyword [C#]
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
ms.openlocfilehash: e73113bd37dbb68590267141ad037f78919520bc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45648924"
---
# <a name="false-operator-c-reference"></a>FALSE-Operator (C#-Referenz)

Gibt den [bool](bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand `false` ist, und gibt ansonsten `false` zurück.

Vor C# 2.0 wurden die Operatoren `true` und `false` verwendet, um benutzerdefinierte Nullable-Werttypen zu erstellen, die mit Typen, wie z. B. `SqlBool` kompatibel waren. Jedoch bietet die Sprache jetzt integrierte Unterstützung für Werttypen, die NULL-Werte zulassen, und diese sollten Sie nach Möglichkeit verwendet, anstatt die Operatoren `true` und `false` zu überladen. Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen](../../programming-guide/nullable-types/index.md).

Bei auf NULL festlegbaren booleschen Werten ist der Ausdruck `a != b` nicht unbedingt gleich `!(a == b)`, da ein oder beide Werte möglicherweise NULL sind. Sie müssen sowohl den Operator `true` als auch den Operator `false` separat überladen, um die NULL-Werte im Ausdruck ordnungsgemäß zu identifizieren. Im folgenden Beispiel wird die Überladung und Verwendung der Operatoren `true` und `false` gezeigt.

[!code-csharp[csrefKeywordsOperator#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#16)]

Ein Typ, der die Operatoren `true` und `false` überlädt, kann für den Kontrollausdruck in den Anweisungen [if](if-else.md), [do](do.md), [while](while.md) und [for](for.md) sowie in [bedingten Ausdrücken](../operators/conditional-operator.md) verwendet werden.

Wenn ein Typ Operator `false` definiert, muss er auch Operator [true](true.md) definieren.

Ein Typ kann nicht direkt die bedingten logischen Operatoren [&&](../operators/conditional-and-operator.md) und [&#124;&#124;](../operators/conditional-or-operator.md) überladen. Jedoch kann ein ähnlicher Effekt erzielt werden, indem die regulären logischen Operatoren sowie die Operatoren `true` und `false` überladen werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [C#-Schlüsselwörter](index.md)  
- [C#-Operatoren](../operators/index.md)  
- [true](true.md)  