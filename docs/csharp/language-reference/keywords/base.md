---
title: base (C#-Referenz)
description: "Erfahren Sie mehr über das base-Schlüsselwort, mit dem aus einer abgeleiteten Klasse auf die Member der Basisklasse zugegriffen werden kann."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 867f9eb286fa7ff5ef3e9167c1ab944c81161216
ms.openlocfilehash: b3a389d92373b6ba5995a7644b0440f9d8fad9ac
ms.contentlocale: de-de
ms.lasthandoff: 08/17/2017

---
# <a name="base-c-reference"></a><span data-ttu-id="f61bc-103">base (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f61bc-103">base (C# Reference)</span></span>

<span data-ttu-id="f61bc-104">Das `base`-Schlüsselwort wird verwendet, um aus einer abgeleiteten Klasse auf die Member der Basisklasse zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="f61bc-104">The `base` keyword is used to access members of the base class from within a derived class:</span></span>

- <span data-ttu-id="f61bc-105">Rufen Sie eine Methode der Basisklasse auf, die durch eine andere Methode überschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="f61bc-105">Call a method on the base class that has been overridden by another method.</span></span>

- <span data-ttu-id="f61bc-106">Geben Sie an, welcher Konstruktor der Basisklasse beim Erstellen von Instanzen der abgeleiteten Klasse aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f61bc-106">Specify which base-class constructor should be called when creating instances of the derived class.</span></span>

<span data-ttu-id="f61bc-107">Zugriff auf eine Basisklasse ist nur in einem Konstruktor, einer Instanzenmethode oder einem Instanzeneigenschaften-Accessor zulässig.</span><span class="sxs-lookup"><span data-stu-id="f61bc-107">A base class access is permitted only in a constructor, an instance method, or an instance property accessor.</span></span>

<span data-ttu-id="f61bc-108">Die Nutzung eines `base`-Schlüsselworts innerhalb einer statischen Methode ist ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="f61bc-108">It is an error to use the `base` keyword from within a static method.</span></span>

<span data-ttu-id="f61bc-109">Die Basisklasse, auf die zugegriffen wird, ist die Basisklasse, die in der Klassendeklaration angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f61bc-109">The base class that is accessed is the base class specified in the class declaration.</span></span> <span data-ttu-id="f61bc-110">Wenn Sie z.B. `class ClassB : ClassA` angeben, wird von ClassB auf die Member von ClassA unabhängig von der Basisklasse von ClassA zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="f61bc-110">For example, if you specify `class ClassB : ClassA`, the members of ClassA are accessed from ClassB, regardless of the base class of ClassA.</span></span>

## <a name="example"></a><span data-ttu-id="f61bc-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f61bc-111">Example</span></span>
<span data-ttu-id="f61bc-112">In diesem Beispiel verfügen sowohl die Basisklasse `Person` als auch die abgeleitete Klasse `Employee` über eine Methode mit dem Namen `Getinfo`.</span><span class="sxs-lookup"><span data-stu-id="f61bc-112">In this example, both the base class, `Person`, and the derived class, `Employee`, have a method named `Getinfo`.</span></span> <span data-ttu-id="f61bc-113">Mithilfe des `base`-Schlüsselworts ist es möglich, die `Getinfo`-Methode der Basisklasse aus der abgeleiteten Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f61bc-113">By using the `base` keyword, it is possible to call the `Getinfo` method on the base class, from within the derived class.</span></span>

<span data-ttu-id="f61bc-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f61bc-114">[!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]</span></span>

<span data-ttu-id="f61bc-115">Weitere Beispiele finden Sie unter [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) und [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="f61bc-115">For additional examples, see [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md), and [override](../../../csharp/language-reference/keywords/override.md).</span></span>

## <a name="example"></a><span data-ttu-id="f61bc-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f61bc-116">Example</span></span>
<span data-ttu-id="f61bc-117">In diesem Beispiel wird veranschaulicht, wie der aufgerufene Konstruktor der Basisklasse beim Erstellen von Instanzen einer abgeleiteten Klasse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f61bc-117">This example shows how to specify the base-class constructor called when creating instances of a derived class.</span></span>

<span data-ttu-id="f61bc-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f61bc-118">[!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f61bc-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f61bc-119">C# language specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f61bc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f61bc-120">See also</span></span>
 <span data-ttu-id="f61bc-121">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f61bc-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f61bc-122">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f61bc-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f61bc-123">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f61bc-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="f61bc-124">this</span><span class="sxs-lookup"><span data-stu-id="f61bc-124">this</span></span>](../../../csharp/language-reference/keywords/this.md)
