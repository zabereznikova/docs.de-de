---
title: base-Schlüsselwort – C#-Referenz
ms.custom: seodec18
description: Erfahren Sie mehr über das base-Schlüsselwort, mit dem aus einer abgeleiteten Klasse auf die Member der Basisklasse zugegriffen werden kann.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: b882a8d1e5979ac184d184be379dd76f7bf3600f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602258"
---
# <a name="base-c-reference"></a><span data-ttu-id="57340-103">base (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="57340-103">base (C# Reference)</span></span>

<span data-ttu-id="57340-104">Das `base`-Schlüsselwort wird verwendet, um aus einer abgeleiteten Klasse auf die Member der Basisklasse zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="57340-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="57340-105">Rufen Sie eine Methode der Basisklasse auf, die durch eine andere Methode überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="57340-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="57340-106">Geben Sie an, welcher Konstruktor der Basisklasse beim Erstellen von Instanzen der abgeleiteten Klasse aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="57340-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="57340-107">Zugriff auf eine Basisklasse ist nur in einem Konstruktor, einer Instanzenmethode oder einem Instanzeneigenschaften-Accessor zulässig.</span><span class="sxs-lookup"><span data-stu-id="57340-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="57340-108">Die Nutzung eines `base`-Schlüsselworts innerhalb einer statischen Methode ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="57340-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="57340-109">Die Basisklasse, auf die zugegriffen wird, ist die Basisklasse, die in der Klassendeklaration angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="57340-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="57340-110">Wenn Sie z.B. `class ClassB : ClassA` angeben, wird von ClassB auf die Member von ClassA unabhängig von der Basisklasse von ClassA zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="57340-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="57340-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57340-111">Example</span></span>

<span data-ttu-id="57340-112">In diesem Beispiel verfügen sowohl die Basisklasse `Person` als auch die abgeleitete Klasse `Employee` über eine Methode mit dem Namen `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="57340-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="57340-113">Mithilfe des `base`-Schlüsselworts ist es möglich, die `Getinfo`-Methode der Basisklasse aus der abgeleiteten Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="57340-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

<span data-ttu-id="57340-114">Weitere Beispiele finden Sie unter [new](new-modifier.md), [virtual](virtual.md) und [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="57340-114">For additional examples, see [new](new-modifier.md), [virtual](virtual.md), and [override](override.md).</span></span>

## <a name="example"></a><span data-ttu-id="57340-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57340-115">Example</span></span>

<span data-ttu-id="57340-116">In diesem Beispiel wird veranschaulicht, wie der aufgerufene Konstruktor der Basisklasse beim Erstellen von Instanzen einer abgeleiteten Klasse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="57340-116">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="57340-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="57340-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="57340-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57340-118">See also</span></span>

- [<span data-ttu-id="57340-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="57340-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="57340-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="57340-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="57340-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="57340-121">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="57340-122">this</span><span class="sxs-lookup"><span data-stu-id="57340-122">this</span></span>](./this.md)
