---
title: Nicht benötigte Coderegeln
description: Erfahren Sie mehr über die Code Analyse für unnötige Code Regeln.
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "96592019"
---
# <a name="unnecessary-code-rules"></a><span data-ttu-id="a9a3a-103">Nicht benötigte Coderegeln</span><span class="sxs-lookup"><span data-stu-id="a9a3a-103">Unnecessary code rules</span></span>

<span data-ttu-id="a9a3a-104">Unnötige Code Regeln identifizieren verschiedene Teile der Codebasis, die unnötig sind und umfaciert oder entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-104">Unnecessary code rules identify different parts of the code base that are unnecessary and can be refactored or removed.</span></span> <span data-ttu-id="a9a3a-105">Das vorhanden sein von unnötigem Code weist auf eines der folgenden Probleme hin:</span><span class="sxs-lookup"><span data-stu-id="a9a3a-105">The presence of unnecessary code indicates one of more of the following problems:</span></span>

- <span data-ttu-id="a9a3a-106">Lesbarkeit: Code, der eine unnötige Herabwürdigung der Lesbarkeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-106">Readability: Code that is unnecessarily degrading readability.</span></span> <span data-ttu-id="a9a3a-107">[IDE0001](ide0001.md) Flags beispielsweise überflüssige Typnamens Qualifizierungen.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-107">For example, [IDE0001](ide0001.md) flags unnecessary type-name qualifications.</span></span>
- <span data-ttu-id="a9a3a-108">Wartbarkeit: Code, der nach dem Refactoring nicht mehr verwendet wird und unnötigerweise gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-108">Maintainability: Code that is no longer used after refactoring and is unnecessarily being maintained.</span></span> <span data-ttu-id="a9a3a-109">[IDE0051](ide0051.md) Flags z. b. nicht verwendete private Felder, Eigenschaften, Ereignisse und Methoden.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-109">For example, [IDE0051](ide0051.md) flags unused private fields, properties, events, and methods.</span></span>
- <span data-ttu-id="a9a3a-110">Leistung: unnötige Berechnung, die keine Nebenwirkungen hat und zu unnötigem Leistungs Aufwand führt.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-110">Performance: Unnecessary computation that has no side effects and leads to unnecessary performance overhead.</span></span> <span data-ttu-id="a9a3a-111">[IDE0059](ide0059.md) Flags z. b. nicht verwendete Wert Zuweisungen, bei denen der Ausdruck zum Berechnen eines Werts keine Nebeneffekte hat.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-111">For example, [IDE0059](ide0059.md) flags unused value assignments where the expression to compute a value has no side effects.</span></span>
- <span data-ttu-id="a9a3a-112">Funktionalität: funktionales Problem im Code, das dazu führt, dass erforderlicher Code redundant ist.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-112">Functionality: Functional issue in code leading to required code being rendered redundant.</span></span> <span data-ttu-id="a9a3a-113">[IDE0060](ide0060.md) Flags z. b. nicht verwendete Parameter, bei denen die Methode versehentlich einen Eingabeparameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-113">For example, [IDE0060](ide0060.md) flags unused parameters where the method accidentally ignores an input parameter.</span></span>

<span data-ttu-id="a9a3a-114">Die Regeln in diesem Abschnitt betreffen die folgenden unnötigen Code Regeln:</span><span class="sxs-lookup"><span data-stu-id="a9a3a-114">The rules in this section concern the following unnecessary code rules:</span></span>

- [<span data-ttu-id="a9a3a-115">Name vereinfachen (IDE0001)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-115">Simplify name (IDE0001)</span></span>](ide0001.md)
- [<span data-ttu-id="a9a3a-116">Vereinfachen des Mitglieds Zugriffs (IDE0002)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-116">Simplify member access (IDE0002)</span></span>](ide0002.md)
- [<span data-ttu-id="a9a3a-117">Unnötige Umwandlung entfernen (IDE0004)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-117">Remove unnecessary cast (IDE0004)</span></span>](ide0004.md)
- [<span data-ttu-id="a9a3a-118">Unnötigen Import entfernen (IDE0005)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-118">Remove unnecessary import (IDE0005)</span></span>](ide0005.md)
- [<span data-ttu-id="a9a3a-119">Entfernen von nicht erreichbarem Code (IDE0035)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-119">Remove unreachable code (IDE0035)</span></span>](ide0035.md)
- [<span data-ttu-id="a9a3a-120">Nicht verwendeten privaten Member entfernen (IDE0051)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-120">Remove unused private member (IDE0051)</span></span>](ide0051.md)
- [<span data-ttu-id="a9a3a-121">Nicht gelesene private Member entfernen (IDE0052)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-121">Remove unread private member (IDE0052)</span></span>](ide0052.md)
- [<span data-ttu-id="a9a3a-122">Nicht verwendeten Ausdruckswert entfernen (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-122">Remove unused expression value (IDE0058)</span></span>](ide0058.md)
- [<span data-ttu-id="a9a3a-123">Unnötige Wert Zuweisung entfernen (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-123">Remove unnecessary value assignment (IDE0059)</span></span>](ide0059.md)
- [<span data-ttu-id="a9a3a-124">Nicht verwendeten Parameter entfernen (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-124">Remove unused parameter (IDE0060)</span></span>](ide0060.md)
- [<span data-ttu-id="a9a3a-125">Unnötige Unterdrückung entfernen (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-125">Remove unnecessary suppression (IDE0079)</span></span>](ide0079.md)
- <span data-ttu-id="a9a3a-126">[Entfernen Sie den unnötigen Unterdrückungs Operator (IDE0080)](ide0080.md) nur c#.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-126">[Remove unnecessary suppression operator (IDE0080)](ide0080.md) - C# only.</span></span>
- <span data-ttu-id="a9a3a-127">[Entfernen Sie "ByVal" (IDE0081)](ide0081.md) nur Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-127">[Remove 'ByVal' (IDE0081)](ide0081.md) - Visual Basic only.</span></span>
- [<span data-ttu-id="a9a3a-128">Unnötigen Gleichheits Operator entfernen (IDE0100)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-128">Remove unnecessary equality operator (IDE0100)</span></span>](ide0100.md)
- <span data-ttu-id="a9a3a-129">[Entfernen Sie unnötige verwerfen (IDE0110)](ide0110.md) nur c#.</span><span class="sxs-lookup"><span data-stu-id="a9a3a-129">[Remove unnecessary discard (IDE0110)](ide0110.md) - C# only.</span></span>

<span data-ttu-id="a9a3a-130">Einige dieser Regeln verfügen über Optionen zum Konfigurieren des Regel Verhaltens:</span><span class="sxs-lookup"><span data-stu-id="a9a3a-130">Some of these rules have options to configure the rule behavior:</span></span>

- [<span data-ttu-id="a9a3a-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-131">csharp_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="a9a3a-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-132">visual_basic_style_unused_value_expression_statement_preference (IDE0058)</span></span>](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [<span data-ttu-id="a9a3a-133">csharp_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-133">csharp_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#csharp_style_unused_value_assignment_preference)
- [<span data-ttu-id="a9a3a-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-134">visual_basic_style_unused_value_assignment_preference (IDE0059)</span></span>](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [<span data-ttu-id="a9a3a-135">dotnet_code_quality_unused_parameters (IDE0060)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-135">dotnet_code_quality_unused_parameters (IDE0060)</span></span>](ide0060.md#dotnet_code_quality_unused_parameters)
- [<span data-ttu-id="a9a3a-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span><span class="sxs-lookup"><span data-stu-id="a9a3a-136">dotnet_remove_unnecessary_suppression_exclusions (IDE0079)</span></span>](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a><span data-ttu-id="a9a3a-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a3a-137">See also</span></span>

- [<span data-ttu-id="a9a3a-138">Regeln für Code Stilsprache</span><span class="sxs-lookup"><span data-stu-id="a9a3a-138">Code style language rules</span></span>](language-rules.md)
- [<span data-ttu-id="a9a3a-139">Codestil-Regel Referenz</span><span class="sxs-lookup"><span data-stu-id="a9a3a-139">Code style rules reference</span></span>](index.md)
