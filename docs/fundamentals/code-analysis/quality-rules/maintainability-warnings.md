---
title: Wart barkeits Regeln (Code Analyse)
description: Erfahren Sie mehr über die wart barkeits Regeln der Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- rules, maintainability
- managed code analysis rules, maintainability rules
- maintainability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: fc2ef2b42eeba241b7af66b579a60365ad2b88c7
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590682"
---
# <a name="maintainability-rules"></a><span data-ttu-id="4b0a6-103">Wartbarkeitsregeln</span><span class="sxs-lookup"><span data-stu-id="4b0a6-103">Maintainability rules</span></span>

<span data-ttu-id="4b0a6-104">Wart barkeits Regeln unterstützen die Verwaltung von Bibliotheken und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-104">Maintainability rules support library and application maintenance.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4b0a6-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4b0a6-105">In this section</span></span>

| <span data-ttu-id="4b0a6-106">Regel</span><span class="sxs-lookup"><span data-stu-id="4b0a6-106">Rule</span></span> | <span data-ttu-id="4b0a6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b0a6-107">Description</span></span> |
|-----------|-----------------------------------|
| [<span data-ttu-id="4b0a6-108">CA1501: Übermäßige Vererbung vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-108">CA1501: Avoid excessive inheritance</span></span>](ca1501.md) | <span data-ttu-id="4b0a6-109">Ein Typ ist in seiner Vererbungshierarchie mehr als vier Ebenen tief.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-109">A type is more than four levels deep in its inheritance hierarchy.</span></span> <span data-ttu-id="4b0a6-110">Tief verschachtelte Typenhierarchien können schwer zu verfolgen, verstehen und verwalten sein.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-110">Deeply nested type hierarchies can be difficult to follow, understand, and maintain.</span></span> |
| [<span data-ttu-id="4b0a6-111">CA1502: Übermäßige Komplexität vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-111">CA1502: Avoid excessive complexity</span></span>](ca1502.md) | <span data-ttu-id="4b0a6-112">Diese Regel ermöglicht Aussagen über die Anzahl linear unabhängiger Pfade in einer Methode, wobei die Anzahl der Pfade durch die Anzahl und Komplexität bedingter Branches bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-112">This rule measures the number of linearly independent paths through the method, which is determined by the number and complexity of conditional branches.</span></span> |
| [<span data-ttu-id="4b0a6-113">CA1505: Nicht wartbaren Code vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-113">CA1505: Avoid unmaintainable code</span></span>](ca1505.md) | <span data-ttu-id="4b0a6-114">Ein Typ oder eine Methode verfügt über einen niedrigen Wartbarkeitsindexwert.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-114">A type or method has a low maintainability index value.</span></span> <span data-ttu-id="4b0a6-115">Ein niedriger Wartbarkeitsindex zeigt an, dass ein Typ oder eine Methode wahrscheinlich schwer zu verwalten ist und geeignet für einen Neuentwurf wäre.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-115">A low maintainability index indicates that a type or method is probably difficult to maintain and would be a good candidate for redesign.</span></span> |
| [<span data-ttu-id="4b0a6-116">CA1506: Übermäßige Klassenkopplungen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-116">CA1506: Avoid excessive class coupling</span></span>](ca1506.md) | <span data-ttu-id="4b0a6-117">Durch diese Regel wird die Klassenkopplung gemessen, indem die eindeutigen Typverweise, die ein Typ oder eine Methode enthält, gezählt werden.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-117">This rule measures class coupling by counting the number of unique type references that a type or method contains.</span></span> |
| [<span data-ttu-id="4b0a6-118">CA1507: „nameof“ anstelle der Zeichenfolge verwenden</span><span class="sxs-lookup"><span data-stu-id="4b0a6-118">CA1507: Use nameof in place of string</span></span>](ca1507.md) | <span data-ttu-id="4b0a6-119">Ein Zeichenfolgenliterals wird als Argument verwendet, bei dem ein- `nameof` Ausdruck verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-119">A string literal is used as an argument where a `nameof` expression could be used.</span></span> |
| [<span data-ttu-id="4b0a6-120">CA1508: Toten Bedingungscode vermeiden</span><span class="sxs-lookup"><span data-stu-id="4b0a6-120">CA1508: Avoid dead conditional code</span></span>](ca1508.md) | <span data-ttu-id="4b0a6-121">Eine Methode verfügt über bedingten Code, der immer zu oder zur Laufzeit ausgewertet wird `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="4b0a6-121">A method has conditional code that always evaluates to `true` or `false` at runtime.</span></span> <span data-ttu-id="4b0a6-122">Dies führt zu einem unzustellbaren Code in der `false` Verzweigung der Bedingung.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-122">This leads to dead code in the `false` branch of the condition.</span></span> |
| [<span data-ttu-id="4b0a6-123">CA1509: Ungültiger Eintrag in der Konfigurationsdatei für die Codemetrik.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-123">CA1509: Invalid entry in code metrics configuration file</span></span>](ca1509.md) | <span data-ttu-id="4b0a6-124">Code metrikregeln, wie z. b. [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) und [CA1506](ca1506.md), haben eine Konfigurationsdatei mit dem Namen mit `CodeMetricsConfig.txt` einem ungültigen Eintrag bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4b0a6-124">Code metrics rules, such as [CA1501](ca1501.md), [CA1502](ca1502.md), [CA1505](ca1505.md) and [CA1506](ca1506.md), supplied a configuration file named `CodeMetricsConfig.txt` that has an invalid entry.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4b0a6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b0a6-125">See also</span></span>

- [<span data-ttu-id="4b0a6-126">Messen von Komplexität und Verwaltbarkeit von verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="4b0a6-126">Measure Complexity and Maintainability of Managed Code</span></span>](/visualstudio/code-quality/code-metrics-values)
