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
ms.openlocfilehash: 4e73b34390143a2ac9b839e1da79b7894232c4b4
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91437877"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="e358b-103">Partieller Typ (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e358b-103">partial type (C# Reference)</span></span>

<span data-ttu-id="e358b-104">Partielle Typdefinitionen ermöglichen, dass die Definition einer Klasse, Struktur, Schnittstelle oder eines Datensatzes in mehrere Dateien aufgeteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e358b-104">Partial type definitions allow for the definition of a class, struct, interface, or record to be split into multiple files.</span></span>

<span data-ttu-id="e358b-105">In *File1.cs*:</span><span class="sxs-lookup"><span data-stu-id="e358b-105">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="e358b-106">Die Deklaration in *File2.cs*:</span><span class="sxs-lookup"><span data-stu-id="e358b-106">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="e358b-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e358b-107">Remarks</span></span>

<span data-ttu-id="e358b-108">Das Aufteilen eines Klassen-, Struktur- oder Schnittstellentyps auf mehrere Dateien kann nützlich sein, wenn Sie mit großen Projekten oder mit automatisch erzeugten Codes arbeiten, wie z.B. denjenigen, die vom [Windows Forms-Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e358b-108">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time).</span></span> <span data-ttu-id="e358b-109">Ein partieller Typ kann eine [partielle Methode](partial-method.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="e358b-109">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="e358b-110">Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e358b-110">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e358b-111">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e358b-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e358b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e358b-112">See also</span></span>

- [<span data-ttu-id="e358b-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e358b-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e358b-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e358b-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e358b-115">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="e358b-115">Modifiers</span></span>](index.md)
- [<span data-ttu-id="e358b-116">Einführung in Generics</span><span class="sxs-lookup"><span data-stu-id="e358b-116">Introduction to Generics</span></span>](../../programming-guide/generics/index.md)
