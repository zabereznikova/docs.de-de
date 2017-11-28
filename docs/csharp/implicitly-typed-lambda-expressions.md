---
title: "Implizit typisierte Lambdaausdrücke"
description: "Erfahren Sie, warum Sie keine implizit typisierte Variablendeklaration verwenden können, um einen Lambdaausdruck zu deklarieren."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a3851da9-e018-4389-9922-233db7d0f841
ms.openlocfilehash: 663613af001f9727c48bd48553540305e47a6bab
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="implicitly-typed-lambda-expressions"></a><span data-ttu-id="3560d-104">Implizit typisierte Lambdaausdrücke</span><span class="sxs-lookup"><span data-stu-id="3560d-104">Implicitly typed lambda expressions</span></span>

<span data-ttu-id="3560d-105">Ich verwenden `var` nicht, um diese Ausdrucksbaumstruktur zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3560d-105">I'm not using `var` to declare this expression tree.</span></span> <span data-ttu-id="3560d-106">Sie können keine implizit typisierte Variablendeklaration verwenden, um einen Lambdaausdruck zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3560d-106">You can't use an implicitly typed variable declaration to declare a lambda expression.</span></span>
<span data-ttu-id="3560d-107">Dadurch entsteht ein zirkuläres logisches Problem für den Compiler.</span><span class="sxs-lookup"><span data-stu-id="3560d-107">It creates a circular logic problem for the compiler.</span></span> <span data-ttu-id="3560d-108">Die Deklaration `var` stellt den Compiler an, den Variablentyp aus dem Ausdruckstyp rechts vom Zuweisungsoperator abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="3560d-108">The `var` declaration tells the compiler to figure out the type of the variable from the type of expression on the right hand side of the assignment operator.</span></span> <span data-ttu-id="3560d-109">Ein Lambdaausdruck hat keinen Kompilierzeittyp, kann aber in jeden beliebigen passenden Delegats- oder Ausdruckstyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="3560d-109">A lambda expression does not have a compile time type, but is convertible to any matching delegate or expression type.</span></span> <span data-ttu-id="3560d-110">Wenn Sie einer Variablen eines Delegats- oder Ausdruckstyps einen Lambdaausdruck zuweisen, sagen Sie damit dem Compiler, dass er den Lambdaausdruck, wenn möglich, in einen Ausdruck oder Delegat konvertieren soll, der der Signatur der zugewiesenen Variablen entspricht.</span><span class="sxs-lookup"><span data-stu-id="3560d-110">When you assign a lambda expression to a variable of a delegate or expression type, you tell the compiler to try and convert the lambda expression into an expression or delegate that matches the signature of the 'assigned to' variable.</span></span> <span data-ttu-id="3560d-111">Der Compiler muss versuchen zu erreichen, dass das Objekt, das sich rechts von der Zuweisung befindet, mit dem Typen links von der Zuweisung übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3560d-111">The compiler must try to make the thing on the right hand side of the assignment match the type on the left hand side of the assignment.</span></span> 

<span data-ttu-id="3560d-112">Die Objekte, die sich jeweils neben dem Compiler befinden, dürfen dem Compiler nicht auftragen, sich das Objekt auf der jeweils anderen Seite des Zuweisungsoperators anzuschauen, um festzustellen, ob der Typ dieses Objekts mit dem jeweils anderen Objekt übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="3560d-112">Both sides of the assignment can't be telling the compiler to look at the object on the other side of the assignment operator and see if my type matches.</span></span>

<span data-ttu-id="3560d-113">Sie können Sich in [diesem Artikel](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) darüber informieren, warum die C#-Programmiersprachen dieses Verhalten vorgibt (zum Download als PDF-Datei)</span><span class="sxs-lookup"><span data-stu-id="3560d-113">You can get even more details on why the C# language specifies that behavior by reading [this article](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/type-inference.pdf) (PDF Download)</span></span>


