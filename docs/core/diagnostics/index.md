---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974148"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="b0699-103">Welche Diagnosetools sind in .NET Core verfügbar?</span><span class="sxs-lookup"><span data-stu-id="b0699-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="b0699-104">Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.</span><span class="sxs-lookup"><span data-stu-id="b0699-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="b0699-105">Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="b0699-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggersmanaged-debuggersmd"></a>[<span data-ttu-id="b0699-106">Verwaltete Debugger</span><span class="sxs-lookup"><span data-stu-id="b0699-106">Managed debuggers</span></span>](managed-debuggers.md)
<span data-ttu-id="b0699-107">Verwaltete Debugger ermöglichen Ihnen die Interaktion mit dem Programm.</span><span class="sxs-lookup"><span data-stu-id="b0699-107">Managed debuggers allow you to interact with your program.</span></span> <span data-ttu-id="b0699-108">Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="b0699-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="b0699-109">Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="b0699-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracinglogging-tracingmd"></a>[<span data-ttu-id="b0699-110">Protokollierung und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="b0699-110">Logging and tracing</span></span>](logging-tracing.md)
<span data-ttu-id="b0699-111">Die Protokollierung und Ablaufverfolgung sind verwandte Techniken.</span><span class="sxs-lookup"><span data-stu-id="b0699-111">Logging and tracing are related techniques.</span></span> <span data-ttu-id="b0699-112">Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="b0699-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="b0699-113">In den Dateien werden die Details eines Programms aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b0699-113">The files record the details of what a program does.</span></span> <span data-ttu-id="b0699-114">Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0699-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="b0699-115">In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="b0699-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testingtestingindexmd"></a>[<span data-ttu-id="b0699-116">Komponententests</span><span class="sxs-lookup"><span data-stu-id="b0699-116">Unit testing</span></span>](../testing/index.md)
<span data-ttu-id="b0699-117">Komponententests sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software.</span><span class="sxs-lookup"><span data-stu-id="b0699-117">Unit testing is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="b0699-118">Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="b0699-118">Unit tests are designed to give you an early warning when you break something.</span></span>
