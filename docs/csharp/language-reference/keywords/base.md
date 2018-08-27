---
title: Schlüsselwort „base“ (C#-Referenz)
description: Erfahren Sie mehr über das base-Schlüsselwort, mit dem aus einer abgeleiteten Klasse auf die Member der Basisklasse zugegriffen werden kann.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: 8719ab79273701173530760ad1bec837c4f4302d
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934352"
---
# <a name="base-c-reference"></a><span data-ttu-id="55981-103">base (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="55981-103">base (C# Reference)</span></span>

<span data-ttu-id="55981-104">Das `base`-Schlüsselwort wird verwendet, um aus einer abgeleiteten Klasse auf die Member der Basisklasse zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="55981-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="55981-105">Rufen Sie eine Methode der Basisklasse auf, die durch eine andere Methode überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="55981-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="55981-106">Geben Sie an, welcher Konstruktor der Basisklasse beim Erstellen von Instanzen der abgeleiteten Klasse aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="55981-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="55981-107">Zugriff auf eine Basisklasse ist nur in einem Konstruktor, einer Instanzenmethode oder einem Instanzeneigenschaften-Accessor zulässig.</span><span class="sxs-lookup"><span data-stu-id="55981-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="55981-108">Die Nutzung eines `base`-Schlüsselworts innerhalb einer statischen Methode ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="55981-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="55981-109">Die Basisklasse, auf die zugegriffen wird, ist die Basisklasse, die in der Klassendeklaration angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="55981-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="55981-110">Wenn Sie z.B. `class ClassB : ClassA` angeben, wird von ClassB auf die Member von ClassA unabhängig von der Basisklasse von ClassA zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="55981-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="55981-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55981-111">Example</span></span>

<span data-ttu-id="55981-112">In diesem Beispiel verfügen sowohl die Basisklasse `Person` als auch die abgeleitete Klasse `Employee` über eine Methode mit dem Namen `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="55981-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="55981-113">Mithilfe des `base`-Schlüsselworts ist es möglich, die `Getinfo`-Methode der Basisklasse aus der abgeleiteten Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="55981-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="55981-114">Weitere Beispiele finden Sie unter [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) und [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="55981-114">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="55981-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55981-115">Example</span></span>

<span data-ttu-id="55981-116">In diesem Beispiel wird veranschaulicht, wie der aufgerufene Konstruktor der Basisklasse beim Erstellen von Instanzen einer abgeleiteten Klasse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="55981-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="55981-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="55981-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="55981-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55981-118">See also</span></span>

- [<span data-ttu-id="55981-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="55981-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="55981-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="55981-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="55981-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="55981-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="55981-122">this</span><span class="sxs-lookup"><span data-stu-id="55981-122">this</span></span>](../../../csharp/language-reference/keywords/this.md)