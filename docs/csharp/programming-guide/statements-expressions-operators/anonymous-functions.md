---
title: Anonyme Funktionen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 078596dcbfd907be53cae2ab3e7dcaa9e311c3f4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588821"
---
# <a name="anonymous-functions-c-programming-guide"></a><span data-ttu-id="2feaf-102">Anonyme Funktionen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2feaf-102">Anonymous functions (C# Programming Guide)</span></span>

<span data-ttu-id="2feaf-103">Eine anonyme Funktion ist eine „Inline“-Anweisung oder ein „Inline“-Ausdruck, der überall dort verwendet werden kann, wo ein Delegattyp erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="2feaf-103">An anonymous function is an "inline" statement or expression that can be used wherever a delegate type is expected.</span></span> <span data-ttu-id="2feaf-104">Sie können sie zum Initialisieren eines benannten Delegaten verwenden oder anstelle eines benannten Delegattypen als Methodenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="2feaf-104">You can use it to initialize a named delegate or pass it instead of a named delegate type as a method parameter.</span></span>

<span data-ttu-id="2feaf-105">Sie können einen [Lambdaausdruck](lambda-expressions.md) oder eine [anonyme Methode](../../language-reference/operators/delegate-operator.md) verwenden, um eine anonyme Funktion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2feaf-105">You can use a [lambda expression](lambda-expressions.md) or an [anonymous method](../../language-reference/operators/delegate-operator.md) to create an anonymous function.</span></span> <span data-ttu-id="2feaf-106">Wir empfehlen die Verwendung von Lambdaausdrücken, da sie eine präzisere und aussagekräftigere Möglichkeit zum Schreiben von Inlinecode bieten.</span><span class="sxs-lookup"><span data-stu-id="2feaf-106">We recommend using lambda expressions as they provide more concise and expressive way to write inline code.</span></span> <span data-ttu-id="2feaf-107">Im Gegensatz zu anonymen Methoden können einige Arten von Lambdaausdrücken in Ausdrucksbaumstrukturtypen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="2feaf-107">Unlike anonymous methods, some types of lambda expressions can be converted to the expression tree types.</span></span>

## <a name="the-evolution-of-delegates-in-c"></a><span data-ttu-id="2feaf-108">Entwicklung von Delegaten in C\#</span><span class="sxs-lookup"><span data-stu-id="2feaf-108">The Evolution of Delegates in C\#</span></span>

 <span data-ttu-id="2feaf-109">In C# 1.0 haben Sie eine Instanz eines Delegaten durch explizites Initialisieren mit einer Methode erstellt, die an anderer Stelle im Code definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2feaf-109">In C# 1.0, you created an instance of a delegate by explicitly initializing it with a method that was defined elsewhere in the code.</span></span> <span data-ttu-id="2feaf-110">C# 2.0 führte das Konzept anonymer Methoden ein, als eine Möglichkeit, unbenannte Inline-Anweisungsblöcke zu schreiben, die in einem Delegataufruf ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2feaf-110">C# 2.0 introduced the concept of anonymous methods as a way to write unnamed inline statement blocks that can be executed in a delegate invocation.</span></span> <span data-ttu-id="2feaf-111">C# 3.0 führte Lambdaausdrücke ein, die anonymen Methoden ähneln, jedoch aussagekräftiger und präziser sind.</span><span class="sxs-lookup"><span data-stu-id="2feaf-111">C# 3.0 introduced lambda expressions, which are similar in concept to anonymous methods but more expressive and concise.</span></span> <span data-ttu-id="2feaf-112">Diese beiden Funktionen werden zusammenfassend als *anonyme Funktionen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2feaf-112">These two features are known collectively as *anonymous functions*.</span></span> <span data-ttu-id="2feaf-113">In der Regel sollten in Anwendungen, die für .NET Framework-Version 3.5 und höher bestimmt sind, Lambdaausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2feaf-113">In general, applications that target version 3.5 and later of the .NET Framework should use lambda expressions.</span></span>  
  
 <span data-ttu-id="2feaf-114">Das folgende Beispiel zeigt die Entwicklung der Delegaterstellung von C# 1.0 zu C# 3.0:</span><span class="sxs-lookup"><span data-stu-id="2feaf-114">The following example demonstrates the evolution of delegate creation from C# 1.0 to C# 3.0:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2feaf-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2feaf-115">C# language specification</span></span>

<span data-ttu-id="2feaf-116">Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2feaf-116">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2feaf-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2feaf-117">See also</span></span>

- [<span data-ttu-id="2feaf-118">Anweisungen, Ausdrücke und Operatoren</span><span class="sxs-lookup"><span data-stu-id="2feaf-118">Statements, Expressions, and Operators</span></span>](./index.md)
- [<span data-ttu-id="2feaf-119">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="2feaf-119">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="2feaf-120">Delegaten</span><span class="sxs-lookup"><span data-stu-id="2feaf-120">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="2feaf-121">Ausdrucksbaumstrukturen (C#)</span><span class="sxs-lookup"><span data-stu-id="2feaf-121">Expression Trees (C#)</span></span>](../concepts/expression-trees/index.md)
