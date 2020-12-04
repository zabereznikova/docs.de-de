---
title: Dokumentations Regeln (Code Analyse)
description: Informationen zu den Dokumentations Regeln für die Code Analyse Regel
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590768"
---
# <a name="documentation-rules"></a><span data-ttu-id="8ba5b-103">Dokumentationsregeln</span><span class="sxs-lookup"><span data-stu-id="8ba5b-103">Documentation rules</span></span>

<span data-ttu-id="8ba5b-104">Dokumentations Regeln unterstützen das Schreiben von gut dokumentierten Bibliotheken durch die korrekte Verwendung von [XML-Dokumentations Kommentaren](../../../csharp/codedoc.md) für extern sichtbare APIs.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-104">Documentation rules support writing well-documented libraries through the correct use of [XML documentation comments](../../../csharp/codedoc.md) for externally visible APIs.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8ba5b-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ba5b-105">In this section</span></span>

| <span data-ttu-id="8ba5b-106">Regel</span><span class="sxs-lookup"><span data-stu-id="8ba5b-106">Rule</span></span> | <span data-ttu-id="8ba5b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ba5b-107">Description</span></span> |
| - | - |
| [<span data-ttu-id="8ba5b-108">CA1200: Verwenden Sie keine cref-Tags mit einem Präfix.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-108">CA1200: Avoid using cref tags with a prefix</span></span>](ca1200.md) | <span data-ttu-id="8ba5b-109">Das Attribut " [kref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) " in einem XML-Dokumenttag bedeutet "Code Verweis".</span><span class="sxs-lookup"><span data-stu-id="8ba5b-109">The [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) attribute in an XML documentation tag means "code reference".</span></span> <span data-ttu-id="8ba5b-110">Es gibt an, dass der innere Text des Tags ein Codeelement ist, wie z.B. ein Typ, eine Methode oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-110">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="8ba5b-111">Vermeiden `cref` Sie die Verwendung von Tags mit Präfixen, da dies verhindert, dass der Compiler Verweise überprüft.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-111">Avoid using `cref` tags with prefixes, because it prevents the compiler from verifying references.</span></span> <span data-ttu-id="8ba5b-112">Außerdem wird verhindert, dass die integrierte Entwicklungsumgebung (IDE) von Visual Studio diese Symbol Verweise bei refactoren findet und aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8ba5b-112">It also prevents the Visual Studio integrated development environment (IDE) from finding and updating these symbol references during refactorings.</span></span> |
