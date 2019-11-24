---
title: C#-Schlüsselwörter
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 9b01b90f0269a0d8e82189276bceae1c5eafb784
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428480"
---
# <a name="c-keywords"></a>C#-Schlüsselwörter

Bei Schlüsselwörtern handelt es sich um vordefinierte reservierte Bezeichner, die eine besondere Bedeutung für den Compiler haben. Sie können nur dann als Bezeichner in einem Programm verwendet werden, wenn `@` als Präfix vorangestellt wird. Beispiel: `@if` ist ein gültiger Bezeichner, aber `if` nicht, da `if` ein Schlüsselwort ist.  
  
 Die erste Tabelle in diesem Thema enthält die Schlüsselwörter, bei denen es sich in jedem Teil eines C#-Programms um reservierte Bezeichner handelt. Die zweite Tabelle in diesem Thema enthält die kontextabhängigen Schlüsselwörter in C#. Kontextabhängige Schlüsselwörter haben nur in einem beschränkten Programmkontext eine besondere Bedeutung und können als Bezeichner außerhalb dieses Kontexts verwendet werden. Im Allgemeinen werden neue Schlüsselwörter als Kontextschlüsselwörter zur C#-Sprache hinzugefügt, um Programme, die mit früheren Versionen geschrieben wurden, nicht zu beschädigen.  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[bool](bool.md)|  
|[break](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](../builtin-types/char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](../builtin-types/floating-point-numeric-types.md)|[default](default.md)|[delegate](../builtin-types/reference-types.md)|  
|[do](do.md)|[double](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[enum](enum.md)|  
|[event](event.md)|[explicit](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](false-literal.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](../builtin-types/floating-point-numeric-types.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[int](../builtin-types/integral-numeric-types.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](../builtin-types/integral-numeric-types.md)|[namespace](namespace.md)|
|[new](../operators/new-operator.md)|[null](null.md)|[object](../builtin-types/reference-types.md)|[operator](../operators/operator-overloading.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](../builtin-types/reference-types.md)|
|[struct](struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](true-literal.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[using](using.md)|[using static](using-static.md)|[virtual](virtual.md)|[void](void.md)|
|[volatile](volatile.md)|[while](while.md)|

## <a name="contextual-keywords"></a>Kontextabhängige Schlüsselwörter

 Ein Kontextschlüsselwort wird verwendet, um eine spezifische Bedeutung im Code bereitzustellen, es ist jedoch kein reserviertes Wort in C#. Einige kontextabhängige Schlüsselwörter, wie `partial` und `where`, haben eine besondere Bedeutung in mindestens zwei Kontexten.  
  
||||  
|---|---|---|  
|[add](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](../operators/await.md)|[by](by.md)|
|[descending](descending.md)|[dynamic](../builtin-types/reference-types.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[global](../operators/namespace-alias-qualifier.md)|
|[group](group-clause.md)|[into](into.md)|[join](join-clause.md)|
|[let](let-clause.md)|[nameof](../operators/nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (Typ)](partial-type.md)|[partial (Methode)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[unmanaged (Einschränkung eines generischen Typs)](where-generic-type-constraint.md)|[value](value.md)|[var](var.md)|
|[when (Filterbedingung)](when.md)|[where (Einschränkung eines generischen Typs)](where-generic-type-constraint.md)|[where (Abfrageklausel)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
