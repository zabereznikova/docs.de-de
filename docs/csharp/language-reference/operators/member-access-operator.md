---
title: sein. -Operator – C#-Referenz
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836460"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2411b-103">sein.</span><span class="sxs-lookup"><span data-stu-id="2411b-103">.</span></span> <span data-ttu-id="2411b-104">operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="2411b-104">operator (C# Reference)</span></span>

<span data-ttu-id="2411b-105">Der Punkt (`.`) wird normalerweise für den Memberzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="2411b-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="2411b-106">Sie verwenden das `.`-Token für den Zugriff auf einen Member eines Namespace oder eines Typs, wie die folgenden Beispiele veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="2411b-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="2411b-107">Verwenden Sie `.` für den Zugriff auf einen geschachtelten Namespace innerhalb eines Namespace, wie im folgenden Beispiel einer [`using`-Anweisung](../keywords/using-directive.md) gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2411b-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="2411b-108">Verwenden Sie `.`, um einen *qualifizierten Namen* zu bilden, um auf einen Typ innerhalb eines Namespace zuzugreifen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2411b-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="2411b-109">Verwenden Sie die [`using`-Anweisung](../keywords/using-directive.md), um die Verwendung qualifizierter Namen optional zu machen.</span><span class="sxs-lookup"><span data-stu-id="2411b-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="2411b-110">Verwenden Sie `.` für den Zugriff auf [Typmember](../../programming-guide/classes-and-structs/index.md#members), statische und nicht statische, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2411b-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="2411b-111">Sie können auch `.` verwenden, um eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2411b-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="2411b-112">Operatorüberladbarkeit</span><span class="sxs-lookup"><span data-stu-id="2411b-112">Operator overloadability</span></span>

<span data-ttu-id="2411b-113">Der Operator `.` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="2411b-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2411b-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2411b-114">C# language specification</span></span>

<span data-ttu-id="2411b-115">Weitere Informationen finden Sie im Abschnitt [Memberzugriff](~/_csharplang/spec/expressions.md#member-access) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2411b-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2411b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2411b-116">See also</span></span>

- [<span data-ttu-id="2411b-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2411b-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2411b-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2411b-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2411b-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2411b-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="2411b-120">[?.- und ?[]-Operatoren](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="2411b-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>