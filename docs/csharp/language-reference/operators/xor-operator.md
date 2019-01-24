---
title: ^-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333706"
---
# <a name="-operator-c-reference"></a>^-Operator (C#-Referenz)

Binäre `^`-Operatoren sind für integrale Typen und `bool` vordefiniert. Für integrale Typen berechnet `^` die bitweise XOR-Operation der Operanden. Für `bool`-Operanden berechnet `^` den XOR-Operator seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn einer und nur einer der Operanden `true` ist.

## <a name="remarks"></a>Hinweise

Benutzerdefinierte Typen können den Operator `^` überladen (weitere Informationen unter [operator](../keywords/operator.md)). Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.

## <a name="example"></a>Beispiel

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

Die Berechnung von `0xf8 ^ 0x3f` im vorherigen Beispiel führt einen bitweisen XOR-Operator der folgenden beiden binären Werte aus, die den Hexadezimalwerten F8 und 3F entsprechen:

`1111 1000`

`0011 1111`

Das Ergebnis von XOR ist `1100 0111`, was hexadezimal C7 ist.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
