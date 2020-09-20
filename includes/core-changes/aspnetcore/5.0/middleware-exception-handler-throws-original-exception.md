---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022965"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="38263-101">Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde</span><span class="sxs-lookup"><span data-stu-id="38263-101">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="38263-102">Vor ASP.NET Core 5.0 führt die [Ausnahmehandlermiddleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) im Falle einer Ausnahme den konfigurierten Ausnahmehandler aus.</span><span class="sxs-lookup"><span data-stu-id="38263-102">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="38263-103">Wenn der Ausnahmehandler, der über <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> konfiguriert wurde, nicht gefunden werden kann, wird eine HTTP 404-Antwort erstellt.</span><span class="sxs-lookup"><span data-stu-id="38263-103">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="38263-104">Die Antwort ist aus den folgenden Gründen irreführend:</span><span class="sxs-lookup"><span data-stu-id="38263-104">The response is misleading in that it:</span></span>

* <span data-ttu-id="38263-105">Anscheinend handelt es sich um einen Benutzerfehler.</span><span class="sxs-lookup"><span data-stu-id="38263-105">Seems to be a user error.</span></span>
* <span data-ttu-id="38263-106">Die Tatsache wird verschleiert, dass auf dem Server eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="38263-106">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="38263-107">Wenn der Ausnahmehandler nicht gefunden werden kann, löst die `ExceptionHandlerMiddleware`-Klasse die ursprüngliche Ausnahme aus, um den irreführenden Fehler in ASP.NET Core 5.0 zu beheben.</span><span class="sxs-lookup"><span data-stu-id="38263-107">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="38263-108">Folglich wird eine HTTP 500-Antwort vom Server erzeugt.</span><span class="sxs-lookup"><span data-stu-id="38263-108">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="38263-109">Beim Debuggen des aufgetretenen Fehlers kann die Antwort in den Serverprotokollen leichter untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="38263-109">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="38263-110">Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="38263-110">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="38263-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="38263-111">Version introduced</span></span>

<span data-ttu-id="38263-112">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="38263-112">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="38263-113">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="38263-113">Old behavior</span></span>

<span data-ttu-id="38263-114">Die Ausnahmehandlermiddleware erzeugt eine HTTP 404-Antwort, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="38263-114">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="38263-115">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="38263-115">New behavior</span></span>

<span data-ttu-id="38263-116">Die Ausnahmehandlermiddleware löst die ursprüngliche Ausnahme aus, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="38263-116">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="38263-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="38263-117">Reason for change</span></span>

<span data-ttu-id="38263-118">Der HTTP 404-Fehler macht nicht deutlich, dass auf dem Server eine Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="38263-118">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="38263-119">Durch diese Änderung wird ein HTTP 500-Fehler erzeugt, um Folgendes zu verdeutlichen:</span><span class="sxs-lookup"><span data-stu-id="38263-119">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="38263-120">Das Problem wird nicht durch einen Benutzerfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="38263-120">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="38263-121">Auf dem Server ist eine Ausnahme aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="38263-121">An exception was encountered on the server.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="38263-122">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="38263-122">Recommended action</span></span>

<span data-ttu-id="38263-123">Es sind keine API-Änderungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38263-123">There are no API changes.</span></span> <span data-ttu-id="38263-124">Alle vorhandenen Apps werden weiterhin kompiliert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="38263-124">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="38263-125">Die ausgelöste Ausnahme wird vom Server verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="38263-125">The exception thrown is handled by the server.</span></span> <span data-ttu-id="38263-126">Die Ausnahme wird beispielsweise in eine HTTP 500-Fehlerantwort von [Kestrel](/aspnet/core/fundamentals/servers/kestrel) oder [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) konvertiert.</span><span class="sxs-lookup"><span data-stu-id="38263-126">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

#### <a name="category"></a><span data-ttu-id="38263-127">Kategorie</span><span class="sxs-lookup"><span data-stu-id="38263-127">Category</span></span>

<span data-ttu-id="38263-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="38263-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="38263-129">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="38263-129">Affected APIs</span></span>

<span data-ttu-id="38263-130">Keine</span><span class="sxs-lookup"><span data-stu-id="38263-130">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
