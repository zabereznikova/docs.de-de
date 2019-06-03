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
ms.openlocfilehash: db3fc477ddf857146072088e49e76855f5390701
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422703"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="fb367-102">Partieller Typ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fb367-102">partial type (C# Reference)</span></span>

<span data-ttu-id="fb367-103">Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur oder Schnittstelle in mehrere Dateien aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="fb367-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="fb367-104">In *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="fb367-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="fb367-105">Die Deklaration in *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="fb367-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="fb367-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="fb367-106">Remarks</span></span>

<span data-ttu-id="fb367-107">Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="fb367-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="fb367-108">Ein partieller Typ kann eine [partielle Methode](partial-method.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb367-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="fb367-109">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="fb367-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fb367-110">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fb367-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fb367-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb367-111">See also</span></span>

- [<span data-ttu-id="fb367-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fb367-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fb367-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fb367-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fb367-114">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="fb367-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="fb367-115">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="fb367-115">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
