---
title: Erstellen meiner ersten Ansprüche unterstützenden ASP.NET Web-Anwendung
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 5a24a2117a031bfe49d0c27dbcefae6db00e6045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792940"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="56795-102">Erstellen meiner ersten Ansprüche unterstützenden ASP.NET Web-Anwendung</span><span class="sxs-lookup"><span data-stu-id="56795-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="56795-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="56795-103">Applies To</span></span>  
  
- <span data-ttu-id="56795-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="56795-104">Windows Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="56795-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="56795-105">ASP.NET</span></span>  
  
 <span data-ttu-id="56795-106">In diesem Thema wird beschrieben, wie Ansprüche unterstützende ASP.NET-Webanwendungen mithilfe von WIF erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="56795-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="56795-107">Normalerweise sind an einem Szenario mit Ansprüche unterstützenden Anwendungen drei Parteien beteiligt: die Anwendung selbst, der Endbenutzer und der Sicherheitstokendienst (STS).</span><span class="sxs-lookup"><span data-stu-id="56795-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="56795-108">Die folgende Abbildung beschreibt dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="56795-108">The following figure describes this scenario:</span></span>  
  
 ![Das Diagramm zeigt eine WIF Basic Web-App-Komponenten.](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1. <span data-ttu-id="56795-110">Die Ansprüche unterstützende Anwendung verwendet WIF, um nicht authentifizierte Anforderungen zu identifizieren und an den STS umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="56795-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2. <span data-ttu-id="56795-111">Der Endbenutzer gibt Anmeldeinformationen für den STS ein, und nach erfolgreicher Authentifizierung gibt der STS ein Token für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="56795-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3. <span data-ttu-id="56795-112">Der Benutzer wird mit dem vom STS ausgegebenen Token in der Anforderung vom STS zur Ansprüche unterstützenden Anwendung umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="56795-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4. <span data-ttu-id="56795-113">Die Ansprüche unterstützende Anwendung wird so konfiguriert, dass sie dem STS und den Token, die sie ausgibt, vertraut.</span><span class="sxs-lookup"><span data-stu-id="56795-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="56795-114">Die Ansprüche unterstützende Anwendung verwendet WIF, um das Token zu überprüfen und zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="56795-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="56795-115">Entwickler verwenden die entsprechende WIF-API und -Typen wie **ClaimsPrincpal** für die Anforderungen der Anwendung, z.B. das Implementieren der entsprechenden Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="56795-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="56795-116">Ab .NET 4.5 ist WIF Bestandteil des .NET Framework-Pakets.</span><span class="sxs-lookup"><span data-stu-id="56795-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="56795-117">Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="56795-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="56795-118">Mit WIF 4.5 müssen keine Out-of-Band-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="56795-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="56795-119">WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="56795-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="56795-120">STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="56795-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="56795-121">Microsoft bietet zwei STS-Dienste nach Industriestandard an:</span><span class="sxs-lookup"><span data-stu-id="56795-121">Microsoft offers two industry standard STS’s:</span></span>  
  
- [<span data-ttu-id="56795-122">Active Directory-Verbunddienste (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="56795-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
- [<span data-ttu-id="56795-123">Windows Azure Access Control Service (ACS)</span><span class="sxs-lookup"><span data-stu-id="56795-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="56795-124">AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56795-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="56795-125">ACS ist ein Cloud-Dienst, der im Rahmen der Microsoft Azure-Plattform angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="56795-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="56795-126">Zu Test- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56795-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="56795-127">Beispielsweise können Sie den lokalen Entwicklungs-STS, der Teil der [Identitäts- und Zugriffstool für Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) das kostenlos online erhältlich ist.</span><span class="sxs-lookup"><span data-stu-id="56795-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="56795-128">Um die erste Ansprüche unterstützende ASP.NET-Anwendung mithilfe von WIF zu erstellen, befolgen Sie die Anweisungen in einem der folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="56795-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
- [<span data-ttu-id="56795-129">How To: Erstellen einer Ansprüche unterstützenden ASP.NET MVC-Web-Anwendung mithilfe von WIF</span><span class="sxs-lookup"><span data-stu-id="56795-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
- [<span data-ttu-id="56795-130">How To: Erstellen von Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF</span><span class="sxs-lookup"><span data-stu-id="56795-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
- [<span data-ttu-id="56795-131">How To: Erstellen von Ansprüche unterstützenden ASP.NET-Anwendung mithilfe der formularbasierten Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="56795-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="56795-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56795-132">See also</span></span>

- [<span data-ttu-id="56795-133">Erste Schritte mit WIF</span><span class="sxs-lookup"><span data-stu-id="56795-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
