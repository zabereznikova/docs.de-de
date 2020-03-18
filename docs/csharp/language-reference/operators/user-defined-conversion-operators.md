---
title: Benutzerdefinierte Konvertierungsoperatoren – C#-Referenz
description: Hier erfahren Sie, wie Sie benutzerdefinierte implizite und explizite Konvertierungen in C# definieren.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: b6061492cc1a4f756196fb8a9050b68651431e38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847265"
---
# <a name="user-defined-conversion-operators-c-reference"></a>Benutzerdefinierte Konvertierungsoperatoren (C#-Referenz)

Ein benutzerdefinierter Typ kann eine benutzerdefinierte implizite oder explizite Konvertierung von einem oder in einen anderen Typ definieren.

Zum Aufrufen von impliziten Konvertierungen ist keine spezielle Syntax erforderlich. Implizite Konvertierungen können in verschiedenen Situationen auftreten, beispielswiese in Arbeitsaufträgen und Methodenaufrufen. Vordefinierte implizite C#-Konvertierungen sind immer erfolgreich und lösen keine Ausnahmen aus. Benutzerdefinierte Konvertierungen sollten sich ebenso verhalten. Wenn bei einer benutzerdefinierten Konvertierung eine Ausnahme ausgelöst werden kann oder Informationen verloren gehen können, definieren Sie sie als explizite Konvertierung.

Benutzerdefinierte Konvertierungen werden vom [is](type-testing-and-cast.md#is-operator)- und [as](type-testing-and-cast.md#as-operator)-Operator nicht berücksichtigt. Verwenden Sie den [cast-Operator ()](type-testing-and-cast.md#cast-operator-), um eine benutzerdefinierte explizite Konvertierung aufzurufen.

Verwenden Sie zum Definieren einer impliziten bzw. expliziten Konvertierung die Schlüsselwörter `operator` und `implicit` bzw. `explicit`. Bei dem Typ, der eine Konvertierung definiert, muss es sich um einen Quelltyp oder um einen Zieltyp dieser Konvertierung handeln. Eine Konvertierung zwischen zwei benutzerdefinierten Typen kann in einem der beiden Typen definiert werden.

Im folgenden Beispiel wird gezeigt, wie eine implizite und eine explizite Konvertierung definiert wird:

[!code-csharp[implicit an explicit conversions](snippets/UserDefinedConversions.cs)]

Sie können auch das Schlüsselwort `operator` verwenden, um einen vordefinierten C#-Operator zu überladen. Weitere Informationen finden Sie unter [Operatorüberladung](operator-overloading.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Konvertierungsoperatoren](~/_csharplang/spec/classes.md#conversion-operators)
- [User-defined conversions (Benutzerdefinierte Konvertierungen)](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions)
- [Explicit conversions (Explizite Konvertierungen)](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Operatorüberladung](operator-overloading.md)
- [Typtest- und Umwandlungsoperatoren](type-testing-and-cast.md)
- [Umwandlung und Typkonvertierung](../../programming-guide/types/casting-and-type-conversions.md)
- [Entwurfsrichtlinien: Konvertierungsoperatoren](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- [Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)
