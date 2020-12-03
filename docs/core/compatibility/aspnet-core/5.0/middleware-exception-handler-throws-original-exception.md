---
title: 'Breaking Change: Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759534"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="8a1a8-103">Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde</span><span class="sxs-lookup"><span data-stu-id="8a1a8-103">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="8a1a8-104">Vor ASP.NET Core 5.0 führt die [Ausnahmehandlermiddleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) im Falle einer Ausnahme den konfigurierten Ausnahmehandler aus.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-104">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="8a1a8-105">Wenn der Ausnahmehandler, der über <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> konfiguriert wurde, nicht gefunden werden kann, wird eine HTTP 404-Antwort erstellt.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-105">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="8a1a8-106">Die Antwort ist aus den folgenden Gründen irreführend:</span><span class="sxs-lookup"><span data-stu-id="8a1a8-106">The response is misleading in that it:</span></span>

* <span data-ttu-id="8a1a8-107">Anscheinend handelt es sich um einen Benutzerfehler.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-107">Seems to be a user error.</span></span>
* <span data-ttu-id="8a1a8-108">Die Tatsache wird verschleiert, dass auf dem Server eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-108">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="8a1a8-109">Wenn der Ausnahmehandler nicht gefunden werden kann, löst die `ExceptionHandlerMiddleware`-Klasse die ursprüngliche Ausnahme aus, um den irreführenden Fehler in ASP.NET Core 5.0 zu beheben.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-109">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="8a1a8-110">Folglich wird eine HTTP 500-Antwort vom Server erzeugt.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-110">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="8a1a8-111">Beim Debuggen des aufgetretenen Fehlers kann die Antwort in den Serverprotokollen leichter untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-111">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="8a1a8-112">Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="8a1a8-112">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8a1a8-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8a1a8-113">Version introduced</span></span>

<span data-ttu-id="8a1a8-114">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="8a1a8-114">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="8a1a8-115">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="8a1a8-115">Old behavior</span></span>

<span data-ttu-id="8a1a8-116">Die Ausnahmehandlermiddleware erzeugt eine HTTP 404-Antwort, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-116">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="8a1a8-117">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="8a1a8-117">New behavior</span></span>

<span data-ttu-id="8a1a8-118">Die Ausnahmehandlermiddleware löst die ursprüngliche Ausnahme aus, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-118">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="8a1a8-119">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="8a1a8-119">Reason for change</span></span>

<span data-ttu-id="8a1a8-120">Der HTTP 404-Fehler macht nicht deutlich, dass auf dem Server eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-120">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="8a1a8-121">Durch diese Änderung wird ein HTTP 500-Fehler erzeugt, um Folgendes zu verdeutlichen:</span><span class="sxs-lookup"><span data-stu-id="8a1a8-121">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="8a1a8-122">Das Problem wird nicht durch einen Benutzerfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-122">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="8a1a8-123">Auf dem Server ist eine Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-123">An exception was encountered on the server.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8a1a8-124">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="8a1a8-124">Recommended action</span></span>

<span data-ttu-id="8a1a8-125">Es sind keine API-Änderungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-125">There are no API changes.</span></span> <span data-ttu-id="8a1a8-126">Alle vorhandenen Apps werden weiterhin kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-126">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="8a1a8-127">Die ausgelöste Ausnahme wird vom Server verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-127">The exception thrown is handled by the server.</span></span> <span data-ttu-id="8a1a8-128">Die Ausnahme wird beispielsweise in eine HTTP 500-Fehlerantwort von [Kestrel](/aspnet/core/fundamentals/servers/kestrel) oder [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8a1a8-128">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8a1a8-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8a1a8-129">Affected APIs</span></span>

<span data-ttu-id="8a1a8-130">Keine</span><span class="sxs-lookup"><span data-stu-id="8a1a8-130">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
