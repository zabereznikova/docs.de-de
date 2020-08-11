---
title: Benutzerdefinierte Konvertierungsoperatoren – C#-Referenz
description: Hier erfahren Sie, wie Sie benutzerdefinierte implizite und explizite Konvertierungen in C# definieren.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
- explicit
- implicit
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: a0eb11d55ad9e9cccde1704ba4c5ae8acb609989
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916628"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Benutzerdefinierte Konvertierungsoperatoren (C#-Referenz)

Ein benutzerdefinierter Typ kann eine benutzerdefinierte implizite oder explizite Konvertierung von einem oder in einen anderen Typ definieren.

Zum Aufrufen von impliziten Konvertierungen ist keine spezielle Syntax erforderlich. Implizite Konvertierungen können in verschiedenen Situationen auftreten, beispielswiese in Arbeitsaufträgen und Methodenaufrufen. Vordefinierte implizite C#-Konvertierungen sind immer erfolgreich und lösen keine Ausnahmen aus. Benutzerdefinierte Konvertierungen sollten sich ebenso verhalten. Wenn bei einer benutzerdefinierten Konvertierung eine Ausnahme ausgelöst werden kann oder Informationen verloren gehen können, definieren Sie sie als explizite Konvertierung.

Benutzerdefinierte Konvertierungen werden vom [is](type-testing-and-cast.md#is-operator)- und [as](type-testing-and-cast.md#as-operator)-Operator nicht berücksichtigt. Verwenden Sie einen [Cast-Ausdruck](type-testing-and-cast.md#cast-expression), um eine benutzerdefinierte explizite Konvertierung aufzurufen.

Verwenden Sie zum Definieren einer impliziten bzw. expliziten Konvertierung die Schlüsselwörter `operator` und `implicit` bzw. `explicit`. Bei dem Typ, der eine Konvertierung definiert, muss es sich um einen Quelltyp oder um einen Zieltyp dieser Konvertierung handeln. Eine Konvertierung zwischen zwei benutzerdefinierten Typen kann in einem der beiden Typen definiert werden.

Im folgenden Beispiel wird gezeigt, wie eine implizite und eine explizite Konvertierung definiert wird:

[!code-csharp[implicit an explicit conversions](snippets/shared/UserDefinedConversions.cs)]

Sie können auch das Schlüsselwort `operator` verwenden, um einen vordefinierten C#-Operator zu überladen. Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Konvertierungsoperatoren](~/_csharplang/spec/classes.md#conversion-operators)
- [User-defined conversions (Benutzerdefinierte Konvertierungen)](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Explicit conversions (Explizite Konvertierungen)](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [Operatorüberladung](operator-overloading.md)
- [Typtest- und Umwandlungsoperatoren](type-testing-and-cast.md)
- [Umwandlung und Typkonvertierung](../../programming-guide/types/casting-and-type-conversions.md)
- [Entwurfsrichtlinien: Konvertierungsoperatoren](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
