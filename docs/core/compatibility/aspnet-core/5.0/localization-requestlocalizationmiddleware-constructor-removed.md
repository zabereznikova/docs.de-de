---
title: 'Breaking Change: Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 53dd0f25078dae140d34d6d21d66983f78b8bdb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759527"
---
# <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="9d18f-103">Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt</span><span class="sxs-lookup"><span data-stu-id="9d18f-103">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="9d18f-104">Der <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>-Konstruktor, dem ein <xref:Microsoft.Extensions.Logging.ILoggerFactory>-Parameter fehlt, wurde [in diesem Commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0) als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="9d18f-104">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="9d18f-105">In ASP.NET Core 5.0 wurde der veraltete Konstruktor entfernt.</span><span class="sxs-lookup"><span data-stu-id="9d18f-105">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="9d18f-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="9d18f-106">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="9d18f-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9d18f-107">Version introduced</span></span>

<span data-ttu-id="9d18f-108">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="9d18f-108">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="9d18f-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="9d18f-109">Old behavior</span></span>

<span data-ttu-id="9d18f-110">Der veraltete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`-Konstruktor ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9d18f-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="9d18f-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="9d18f-111">New behavior</span></span>

<span data-ttu-id="9d18f-112">Der veraltete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`-Konstruktor ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9d18f-112">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="9d18f-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="9d18f-113">Reason for change</span></span>

<span data-ttu-id="9d18f-114">Diese Änderung sorgt dafür, dass die Middleware für die Anforderungslokalisierung immer Zugriff auf die Protokollierung hat.</span><span class="sxs-lookup"><span data-stu-id="9d18f-114">This change ensures that the request localization middleware always has access to a logger.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="9d18f-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="9d18f-115">Recommended action</span></span>

<span data-ttu-id="9d18f-116">Wenn eine `RequestLocalizationMiddleware`-Instanz manuell erstellt wird, übergeben Sie eine `ILoggerFactory`-Instanz im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9d18f-116">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="9d18f-117">Wenn in diesem Kontext keine gültige `ILoggerFactory`-Instanz verfügbar ist, sollten Sie den Middlewarekonstruktor eine <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory>-Instanz übergeben.</span><span class="sxs-lookup"><span data-stu-id="9d18f-117">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="9d18f-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9d18f-118">Affected APIs</span></span>

[<span data-ttu-id="9d18f-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="9d18f-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

### Category

ASP.NET Core

### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
