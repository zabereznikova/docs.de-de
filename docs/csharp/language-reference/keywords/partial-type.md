---
title: Partieller Typ – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 7af43a25f88ff0a53e5fa257b13bb1dc8a6d55eb
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422602"
---
# <a name="partial-type-c-reference"></a>Partieller Typ (C#-Referenz)

Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur oder Schnittstelle in mehrere Dateien aufgeteilt wird.

In *File1.cs*:

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

Die Deklaration in *File2.cs*:

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a>Anmerkungen

Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md) bereitgestellt werden. Ein partieller Typ kann eine [partielle Methode](partial-method.md) enthalten. Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Modifizierer](index.md)
- [Einführung in Generics](../../programming-guide/generics/index.md)
