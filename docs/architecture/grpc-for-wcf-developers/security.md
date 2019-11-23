---
title: 'Sicherheit in GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Übersicht über die Authentifizierung und Autorisierung von Anrufen und Kanälen in GrpC.
ms.date: 09/02/2019
ms.openlocfilehash: b88ed0c01d1ca4432c7e4fe7115246f4227159df
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967251"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="d3813-103">Sicherheit in gRPC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="d3813-103">Security in gRPC applications</span></span>

<span data-ttu-id="d3813-104">In jedem realen Szenario ist das Sichern von Anwendungen und Diensten von entscheidender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="d3813-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="d3813-105">Die Sicherheit deckt drei wichtige Bereiche ab: das Verschlüsseln von Netzwerk Datenverkehr, um zu verhindern, dass Sie von böswilligen Actors abgefangen werden. Authentifizieren von Clients und Servern zum Einrichten von Identität und Vertrauensstellung und autorisierender Clients zum Steuern des Zugriffs auf Systeme und Anwenden von Berechtigungen basierend auf der Identität.</span><span class="sxs-lookup"><span data-stu-id="d3813-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="d3813-106">Bei der **Authentifizierung** wird die Identität eines Clients oder Servers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d3813-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="d3813-107">Bei der **Autorisierung** wird bestimmt, ob ein Client über die Berechtigung verfügt, auf eine Ressource zuzugreifen oder einen Befehl auszugeben.</span><span class="sxs-lookup"><span data-stu-id="d3813-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="d3813-108">In diesem Kapitel werden die Funktionen für die Authentifizierung und Autorisierung in GrpC für ASP.net Core behandelt und die Netzwerksicherheit mithilfe von TLS-verschlüsselten Verbindungen erörtert.</span><span class="sxs-lookup"><span data-stu-id="d3813-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="d3813-109">WCF-Authentifizierung und-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="d3813-109">WCF authentication and authorization</span></span>

<span data-ttu-id="d3813-110">In WCF wurden Authentifizierung und Autorisierung je nach verwendeter Transporte und Bindungen auf unterschiedliche Weise gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="d3813-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="d3813-111">WCF unterstützte verschiedene WS-\*-Sicherheitsstandards sowie die Windows-Authentifizierung für HTTP-Dienste, die in IIS oder NetTcp-Diensten zwischen Windows-Systemen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d3813-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="d3813-112">GrpC-Authentifizierung und-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="d3813-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="d3813-113">die GrpC-Authentifizierung und-Autorisierung funktioniert auf zwei Ebenen.</span><span class="sxs-lookup"><span data-stu-id="d3813-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="d3813-114">Die Authentifizierung/Autorisierung auf aufrufsebene wird in der Regel mithilfe von Token gehandhabt, die bei der Anforderung in Metadaten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3813-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="d3813-115">Bei der Authentifizierung auf Kanal Ebene wird ein Client Zertifikat verwendet, das auf der Verbindungs Ebene angewendet wird. Außerdem können Authentifizierungs-/autorisierungsanmelde-Anmelde Informationen auf Aufrufebene enthalten sein, die automatisch auf jeden Kanal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d3813-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="d3813-116">Sie können einen oder beide dieser Mechanismen verwenden, um den Dienst zu sichern.</span><span class="sxs-lookup"><span data-stu-id="d3813-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="d3813-117">Die ASP.net Core-Implementierung von GrpC unterstützt die Authentifizierung und Autorisierung unter Verwendung der meisten Standard ASP.net Core Mechanismen:</span><span class="sxs-lookup"><span data-stu-id="d3813-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="d3813-118">Rückruf Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d3813-118">Call authentication</span></span>
  - <span data-ttu-id="d3813-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d3813-119">Azure Active Directory</span></span>
  - <span data-ttu-id="d3813-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="d3813-120">IdentityServer</span></span>
  - <span data-ttu-id="d3813-121">JWT-bearertoken</span><span class="sxs-lookup"><span data-stu-id="d3813-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="d3813-122">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="d3813-122">OAuth 2.0</span></span>
  - <span data-ttu-id="d3813-123">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="d3813-123">OpenID Connect</span></span>
  - <span data-ttu-id="d3813-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="d3813-124">WS-Federation</span></span>
- <span data-ttu-id="d3813-125">Kanal Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d3813-125">Channel authentication</span></span>
  - <span data-ttu-id="d3813-126">Clientzertifikat</span><span class="sxs-lookup"><span data-stu-id="d3813-126">Client Certificate</span></span>

<span data-ttu-id="d3813-127">Die Methoden zum Abrufen von Authentifizierungsmethoden basieren alle auf *Token*.</span><span class="sxs-lookup"><span data-stu-id="d3813-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="d3813-128">Der einzige wirkliche Unterschied ist die Art und Weise, wie das Token generiert wird, und die Bibliotheken, die zum Überprüfen der Token im ASP.net Core Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3813-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="d3813-129">Weitere Informationen finden Sie in der [Dokumentation zur Authentifizierung und Autorisierung auf Microsoft-Dokumentation](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="d3813-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="d3813-130">Wenn Sie GrpC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanal Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3813-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="d3813-131">In diesem Kapitel wird erläutert, wie Sie Anmelde Informationen und channelanmelde Informationen für einen GrpC-Dienst anwenden und wie Sie Anmelde Informationen von einem .net Core-GrpC-Client verwenden, um sich beim Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="d3813-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d3813-132">[Zurück](client-libraries.md)
>[Weiter](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="d3813-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
