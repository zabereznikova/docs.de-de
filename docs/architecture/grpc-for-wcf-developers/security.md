---
title: Sicherheit in gRPC-Anwendungen - gRPC für WCF-Entwickler
description: Übersicht über die Anruf- und Kanalauthentifizierung und Autorisierung in gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147814"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="72846-103">Sicherheit in gRPC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="72846-103">Security in gRPC applications</span></span>

<span data-ttu-id="72846-104">In jedem realen Szenario ist die Sicherung von Anwendungen und Diensten unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="72846-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="72846-105">Die Sicherheit umfasst drei Schlüsselbereiche:</span><span class="sxs-lookup"><span data-stu-id="72846-105">Security covers three key areas:</span></span>

* <span data-ttu-id="72846-106">Verschlüsseln des Netzwerkverkehrs, um zu verhindern, dass böswillige Hacker ihn abfangen.</span><span class="sxs-lookup"><span data-stu-id="72846-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="72846-107">Authentifizieren von Clients und Servern zum Einrichten von Identität und Vertrauen.</span><span class="sxs-lookup"><span data-stu-id="72846-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="72846-108">Autorisiert Clients, den Zugriff auf Systeme zu steuern und Berechtigungen basierend auf der Identität anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="72846-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="72846-109">Bei der *Authentifizierung* geht es um das Ermitteln der Identität eines Clients oder Servers.</span><span class="sxs-lookup"><span data-stu-id="72846-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="72846-110">*Bei* der Autorisierung geht es darum, zu ermitteln, ob ein Client über die Berechtigung zum Zugriff auf eine Ressource oder zum Ausgeben eines Befehls verfügt.</span><span class="sxs-lookup"><span data-stu-id="72846-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="72846-111">In diesem Kapitel werden die Authentifizierungs- und Autorisierungsmöglichkeiten in gRPC für ASP.NET Core behandelt.</span><span class="sxs-lookup"><span data-stu-id="72846-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="72846-112">Außerdem wird die Netzwerksicherheit über TLS-verschlüsselte Verbindungen erörtert.</span><span class="sxs-lookup"><span data-stu-id="72846-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="72846-113">WCF-Authentifizierung und -Autorisierung</span><span class="sxs-lookup"><span data-stu-id="72846-113">WCF authentication and authorization</span></span>

<span data-ttu-id="72846-114">In Windows Communication Foundation (WCF) wurden Authentifizierung und Autorisierung je nach verwendeten Transporten und Bindungen auf unterschiedliche Weise behandelt.</span><span class="sxs-lookup"><span data-stu-id="72846-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="72846-115">WCF unterstützte verschiedene\* WS-Sicherheitsstandards.</span><span class="sxs-lookup"><span data-stu-id="72846-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="72846-116">Es unterstützte auch die Windows-Authentifizierung für HTTP-Dienste, die in IIS- oder NetTCP-Diensten zwischen Windows-Systemen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="72846-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="72846-117">gRPC-Authentifizierung und -Autorisierung</span><span class="sxs-lookup"><span data-stu-id="72846-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="72846-118">die gRPC-Authentifizierung und -Autorisierung funktioniert auf zwei Ebenen:</span><span class="sxs-lookup"><span data-stu-id="72846-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="72846-119">Die Authentifizierung/Autorisierung auf Anrufebene wird in der Regel über Token behandelt, die bei einem Aufruf in Metadaten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="72846-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="72846-120">Die Authentifizierung auf Kanalebene verwendet ein Clientzertifikat, das auf Verbindungsebene angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="72846-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="72846-121">Es kann auch Authentifizierungs-/Autorisierungsanmeldeinformationen auf Aufrufebene enthalten, die auf jeden Aufruf des Kanals automatisch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="72846-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="72846-122">Sie können einen oder beide dieser Mechanismen verwenden, um Ihren Dienst zu sichern.</span><span class="sxs-lookup"><span data-stu-id="72846-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="72846-123">Die ASP.NET Core-Implementierung von gRPC unterstützt die Authentifizierung und Autorisierung über die meisten Standard-ASP.NET Core-Mechanismen:</span><span class="sxs-lookup"><span data-stu-id="72846-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="72846-124">Anrufauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="72846-124">Call authentication</span></span>
  - <span data-ttu-id="72846-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="72846-125">Azure Active Directory</span></span>
  - <span data-ttu-id="72846-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="72846-126">IdentityServer</span></span>
  - <span data-ttu-id="72846-127">JWT-Trägertoken</span><span class="sxs-lookup"><span data-stu-id="72846-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="72846-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="72846-128">OAuth 2.0</span></span>
  - <span data-ttu-id="72846-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="72846-129">OpenID Connect</span></span>
  - <span data-ttu-id="72846-130">WS-Federation-</span><span class="sxs-lookup"><span data-stu-id="72846-130">WS-Federation</span></span>
- <span data-ttu-id="72846-131">Kanalauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="72846-131">Channel authentication</span></span>
  - <span data-ttu-id="72846-132">Clientzertifikat</span><span class="sxs-lookup"><span data-stu-id="72846-132">Client certificate</span></span>

<span data-ttu-id="72846-133">Die *Aufrufauthentifizierungsmethoden*basieren alle auf Token .</span><span class="sxs-lookup"><span data-stu-id="72846-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="72846-134">Der einzige wirkliche Unterschied besteht darin, wie die Token generiert werden und welche Bibliotheken zum Überprüfen der Token im ASP.NET Core-Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72846-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="72846-135">Weitere Informationen finden Sie im [Authentifizierungs- und Autorisierungsartikel.](/aspnet/core/grpc/authn-and-authz)</span><span class="sxs-lookup"><span data-stu-id="72846-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="72846-136">Wenn Sie gRPC über eine TLS-verschlüsselte HTTP/2-Verbindung verwenden, wird der gesamte Datenverkehr zwischen Clients und Servern verschlüsselt, auch wenn Sie keine Authentifizierung auf Kanalebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="72846-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="72846-137">In diesem Kapitel wird gezeigt, wie Anrufanmeldeinformationen und Channel-Anmeldeinformationen auf einen gRPC-Dienst angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="72846-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="72846-138">Außerdem wird gezeigt, wie Anmeldeinformationen von einem .NET Core gRPC-Client verwendet werden, um sich beim Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="72846-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="72846-139">[VorherigeS](client-libraries.md)
>[Weiter](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="72846-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
