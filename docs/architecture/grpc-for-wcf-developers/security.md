---
title: 'Sicherheit in GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Übersicht über die Authentifizierung und Autorisierung von Anrufen und Kanälen in GrpC.
ms.date: 12/15/2020
ms.openlocfilehash: a5c16a4a4f7567e23bf4f9e3049fe116086daf12
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938090"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="0c037-103">Sicherheit in gRPC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="0c037-103">Security in gRPC applications</span></span>

<span data-ttu-id="0c037-104">In jedem realen Szenario ist das Sichern von Anwendungen und Diensten von entscheidender Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="0c037-104">In any real-world scenario, securing applications and services are essential.</span></span> <span data-ttu-id="0c037-105">Sicherheit deckt drei wichtige Bereiche ab:</span><span class="sxs-lookup"><span data-stu-id="0c037-105">Security covers three key areas:</span></span>

* <span data-ttu-id="0c037-106">Verschlüsseln von Netzwerk Datenverkehr, um zu verhindern, dass böswillige Hacker Sie abfangen.</span><span class="sxs-lookup"><span data-stu-id="0c037-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="0c037-107">Authentifizieren von Clients und Servern, um Identität und Vertrauensstellung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="0c037-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="0c037-108">Autorisierungs Clients zum Steuern des Zugriffs auf Systeme und Anwenden von Berechtigungen basierend auf der Identität.</span><span class="sxs-lookup"><span data-stu-id="0c037-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="0c037-109">Bei der *Authentifizierung* wird die Identität eines Clients oder Servers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0c037-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="0c037-110">Bei der *Autorisierung* wird bestimmt, ob ein Client über die Berechtigung verfügt, auf eine Ressource zuzugreifen oder einen Befehl auszugeben.</span><span class="sxs-lookup"><span data-stu-id="0c037-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="0c037-111">In diesem Kapitel werden die Funktionen für die Authentifizierung und Autorisierung in GrpC für ASP.net Core behandelt.</span><span class="sxs-lookup"><span data-stu-id="0c037-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="0c037-112">Außerdem wird die Netzwerksicherheit über TLS-verschlüsselte Verbindungen erörtert.</span><span class="sxs-lookup"><span data-stu-id="0c037-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="0c037-113">WCF-Authentifizierung und-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="0c037-113">WCF authentication and authorization</span></span>

<span data-ttu-id="0c037-114">In Windows Communication Foundation (WCF) wurden die Authentifizierung und die Autorisierung auf unterschiedliche Weise verarbeitet, je nachdem, welche Transporte und Bindungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c037-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="0c037-115">WCF unterstützte verschiedene WS- \* Sicherheitsstandards.</span><span class="sxs-lookup"><span data-stu-id="0c037-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="0c037-116">Außerdem wird die Windows-Authentifizierung für HTTP-Dienste unterstützt, die in IIS oder NetTcp-Diensten zwischen Windows-Systemen ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="0c037-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="0c037-117">GrpC-Authentifizierung und-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="0c037-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="0c037-118">die GrpC-Authentifizierung und-Autorisierung funktioniert auf zwei Ebenen:</span><span class="sxs-lookup"><span data-stu-id="0c037-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="0c037-119">Die Authentifizierung/Autorisierung auf aufrufsebene wird in der Regel durch Token verarbeitet, die beim Ausführen des Aufrufens in Metadaten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c037-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="0c037-120">Bei der Authentifizierung auf Kanal Ebene wird ein Client Zertifikat verwendet, das auf der Verbindungs Ebene angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c037-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="0c037-121">Außerdem können Authentifizierungs-/autorisierungsanmelde-Anmelde Informationen auf Aufrufebene enthalten sein, die automatisch auf jeden Kanal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c037-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="0c037-122">Sie können einen oder beide dieser Mechanismen verwenden, um den Dienst zu sichern.</span><span class="sxs-lookup"><span data-stu-id="0c037-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="0c037-123">Die ASP.net Core-Implementierung von GrpC unterstützt die Authentifizierung und Autorisierung über die meisten Standard ASP.net Core Mechanismen:</span><span class="sxs-lookup"><span data-stu-id="0c037-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="0c037-124">Rückruf Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c037-124">Call authentication</span></span>
  - <span data-ttu-id="0c037-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0c037-125">Azure Active Directory</span></span>
  - <span data-ttu-id="0c037-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="0c037-126">IdentityServer</span></span>
  - <span data-ttu-id="0c037-127">JWT-bearertoken</span><span class="sxs-lookup"><span data-stu-id="0c037-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="0c037-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="0c037-128">OAuth 2.0</span></span>
  - <span data-ttu-id="0c037-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="0c037-129">OpenID Connect</span></span>
  - <span data-ttu-id="0c037-130">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="0c037-130">WS-Federation</span></span>
- <span data-ttu-id="0c037-131">Kanal Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c037-131">Channel authentication</span></span>
  - <span data-ttu-id="0c037-132">Clientzertifikat</span><span class="sxs-lookup"><span data-stu-id="0c037-132">Client certificate</span></span>

<span data-ttu-id="0c037-133">Die Methoden zum Abrufen von Authentifizierungsmethoden basieren alle auf *Token*.</span><span class="sxs-lookup"><span data-stu-id="0c037-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="0c037-134">Der einzige wirkliche Unterschied ist die Art und Weise, wie die Token generiert werden, und die Bibliotheken, die zum Überprüfen der Token im ASP.net Core Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c037-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="0c037-135">Weitere Informationen finden Sie im Artikel zur [Authentifizierung und Autorisierung](/aspnet/core/grpc/authn-and-authz) .</span><span class="sxs-lookup"><span data-stu-id="0c037-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="0c037-136">Wenn Sie GrpC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanal Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c037-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="0c037-137">In diesem Kapitel wird erläutert, wie Sie Anmelde Informationen und channelanmelde Informationen auf einen GrpC-Dienst anwenden.</span><span class="sxs-lookup"><span data-stu-id="0c037-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="0c037-138">Außerdem wird gezeigt, wie Anmelde Informationen von einem .net-GrpC-Client für die Authentifizierung beim Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c037-138">It will also show how to use credentials from a .NET gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0c037-139">[Zurück](client-libraries.md)
>[Weiter](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="0c037-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
