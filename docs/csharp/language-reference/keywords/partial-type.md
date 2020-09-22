---
description: Partieller Typ – C#-Referenz
title: Partieller Typ – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 0445ac33473c7e2d1916705893b22ba21bb981ff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536845"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="a2c7c-103">Partieller Typ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a2c7c-103">partial type (C# Reference)</span></span>

<span data-ttu-id="a2c7c-104">Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur oder Schnittstelle in mehrere Dateien aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="a2c7c-104">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="a2c7c-105">In *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="a2c7c-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="a2c7c-106">Die Deklaration in *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="a2c7c-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="a2c7c-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a2c7c-107">Remarks</span></span>

<span data-ttu-id="a2c7c-108">Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a2c7c-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="a2c7c-109">Ein partieller Typ kann eine [partielle Methode](partial-method.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2c7c-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="a2c7c-110">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a2c7c-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a2c7c-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a2c7c-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a2c7c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2c7c-112">See also</span></span>

- [<span data-ttu-id="a2c7c-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a2c7c-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2c7c-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a2c7c-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2c7c-115">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="a2c7c-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="a2c7c-116">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="a2c7c-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
