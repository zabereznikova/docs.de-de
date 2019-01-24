---
title: ^=-Operator – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333550"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="5c74c-102">^=-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5c74c-102">^= operator (C# Reference)</span></span>

<span data-ttu-id="5c74c-103">Der XOR-Zuweisungsoperator („exklusives Oder“)</span><span class="sxs-lookup"><span data-stu-id="5c74c-103">The exclusive-OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c74c-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c74c-104">Remarks</span></span>

<span data-ttu-id="5c74c-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="5c74c-105">An expression of the form</span></span>

```csharp
x ^= y
```

<span data-ttu-id="5c74c-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="5c74c-106">is evaluated as</span></span>

```csharp
x = x ^ y
```

<span data-ttu-id="5c74c-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="5c74c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="5c74c-108">Der [Operator ^](xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../keywords/bool.md)-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="5c74c-108">The [^ operator](xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="5c74c-109">Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](xor-operator.md) überladen (weitere Informationen unter [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="5c74c-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](xor-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="5c74c-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c74c-110">Example</span></span>

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a><span data-ttu-id="5c74c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c74c-111">See also</span></span>

- [<span data-ttu-id="5c74c-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5c74c-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5c74c-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5c74c-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5c74c-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="5c74c-114">C# operators</span></span>](index.md)