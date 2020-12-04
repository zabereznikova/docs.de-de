---
title: Portabilität und Interoperabilitäts Regeln (Code Analyse)
description: Informationen zu Portabilität und Interoperabilitäts Regeln für die Code Analyse Regel
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "96590683"
---
# <a name="portability-and-interoperability-rules"></a><span data-ttu-id="dc35c-103">Portabilitäts- und Interoperabilitätsregeln</span><span class="sxs-lookup"><span data-stu-id="dc35c-103">Portability and interoperability rules</span></span>

<span data-ttu-id="dc35c-104">Portabilitäts Regeln unterstützen Portabilität auf verschiedenen Plattformen</span><span class="sxs-lookup"><span data-stu-id="dc35c-104">Portability rules support portability across different platforms.</span></span> <span data-ttu-id="dc35c-105">Interoperabilitäts Regeln unterstützen Interaktionen mit com-Clients.</span><span class="sxs-lookup"><span data-stu-id="dc35c-105">Interoperability rules support interaction with COM clients.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="dc35c-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dc35c-106">In this section</span></span>

| <span data-ttu-id="dc35c-107">Regel</span><span class="sxs-lookup"><span data-stu-id="dc35c-107">Rule</span></span> | <span data-ttu-id="dc35c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc35c-108">Description</span></span> |
| - | - |
| [<span data-ttu-id="dc35c-109">CA1401: P/Aufrufe dürfen nicht sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="dc35c-109">CA1401: P/Invokes should not be visible</span></span>](ca1401.md) | <span data-ttu-id="dc35c-110">Eine öffentliche oder geschützte Methode in einem öffentlichen Typ weist das System.Runtime.InteropServices.DllImportAttribute-Attribut auf (wird auch vom Declare-Schlüsselwort in Visual Basic implementiert).</span><span class="sxs-lookup"><span data-stu-id="dc35c-110">A public or protected method in a public type has the System.Runtime.InteropServices.DllImportAttribute attribute (also implemented by the Declare keyword in Visual Basic).</span></span> <span data-ttu-id="dc35c-111">Solche Methoden sollten nicht verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="dc35c-111">Such methods should not be exposed.</span></span> |
| [<span data-ttu-id="dc35c-112">CA1416: Plattformkompatibilität überprüfen</span><span class="sxs-lookup"><span data-stu-id="dc35c-112">CA1416: Validate platform compatibility</span></span>](ca1416.md) | <span data-ttu-id="dc35c-113">Durch die Verwendung von Platt Form abhängigen APIs in einer Komponente wird der Code nicht mehr auf allen Plattformen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="dc35c-113">Using platform-dependent APIs on a component makes the code no longer work across all platforms.</span></span> |
| [<span data-ttu-id="dc35c-114">CA1417: nicht `OutAttribute` für Zeichen folgen Parameter für P/Aufrufe verwenden</span><span class="sxs-lookup"><span data-stu-id="dc35c-114">CA1417: Do not use `OutAttribute` on string parameters for P/Invokes</span></span>](ca1417.md) | <span data-ttu-id="dc35c-115">Zeichen folgen Parameter, die mit dem als Wert übermittelt werden, `OutAttribute` können die Laufzeit destabilisieren, wenn die Zeichenfolge eine Internpool vorhanden Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="dc35c-115">String parameters passed by value with the `OutAttribute` can destabilize the runtime if the string is an interned string.</span></span> |
