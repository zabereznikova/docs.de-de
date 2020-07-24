---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309147"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a><span data-ttu-id="accba-101">Lokalisierung: Ein veralteter Konstruktor wurde in der Middleware für Anforderungslokalisierung entfernt</span><span class="sxs-lookup"><span data-stu-id="accba-101">Localization: Obsolete constructor removed in request localization middleware</span></span>

<span data-ttu-id="accba-102">Der <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware>-Konstruktor, dem ein <xref:Microsoft.Extensions.Logging.ILoggerFactory>-Parameter fehlt, wurde [in diesem Commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0) als veraltet gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="accba-102">The <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> constructor that lacks an <xref:Microsoft.Extensions.Logging.ILoggerFactory> parameter was marked as obsolete [in this commit](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0).</span></span> <span data-ttu-id="accba-103">In ASP.NET Core 5.0 wurde der veraltete Konstruktor entfernt.</span><span class="sxs-lookup"><span data-stu-id="accba-103">In ASP.NET Core 5.0, the obsolete constructor was removed.</span></span> <span data-ttu-id="accba-104">Weitere Informationen finden Sie unter [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span><span class="sxs-lookup"><span data-stu-id="accba-104">For discussion, see [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="accba-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="accba-105">Version introduced</span></span>

<span data-ttu-id="accba-106">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="accba-106">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="accba-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="accba-107">Old behavior</span></span>

<span data-ttu-id="accba-108">Der veraltete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`-Konstruktor ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="accba-108">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor exists.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="accba-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="accba-109">New behavior</span></span>

<span data-ttu-id="accba-110">Der veraltete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)`-Konstruktor ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="accba-110">The obsolete `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` constructor doesn't exist.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="accba-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="accba-111">Reason for change</span></span>

<span data-ttu-id="accba-112">Diese Änderung sorgt dafür, dass die Middleware für die Anforderungslokalisierung immer Zugriff auf die Protokollierung hat.</span><span class="sxs-lookup"><span data-stu-id="accba-112">This change ensures that the request localization middleware always has access to a logger.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="accba-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="accba-113">Recommended action</span></span>

<span data-ttu-id="accba-114">Wenn eine `RequestLocalizationMiddleware`-Instanz manuell erstellt wird, übergeben Sie eine `ILoggerFactory`-Instanz im Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="accba-114">When manually constructing an instance of `RequestLocalizationMiddleware`, pass an `ILoggerFactory` instance in the constructor.</span></span> <span data-ttu-id="accba-115">Wenn in diesem Kontext keine gültige `ILoggerFactory`-Instanz verfügbar ist, sollten Sie den Middlewarekonstruktor eine <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory>-Instanz übergeben.</span><span class="sxs-lookup"><span data-stu-id="accba-115">If a valid `ILoggerFactory` instance isn't available in that context, consider passing the middleware constructor a <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> instance.</span></span>

#### <a name="category"></a><span data-ttu-id="accba-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="accba-116">Category</span></span>

<span data-ttu-id="accba-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="accba-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="accba-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="accba-118">Affected APIs</span></span>

[<span data-ttu-id="accba-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span><span class="sxs-lookup"><span data-stu-id="accba-119">RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)</span></span>](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
