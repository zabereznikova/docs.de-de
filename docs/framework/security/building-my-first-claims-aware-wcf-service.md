---
title: "Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: f5641eba212cfdeb95c0a52a82a28b5c2d3e9aee
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="079e6-102">Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts</span><span class="sxs-lookup"><span data-stu-id="079e6-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="079e6-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="079e6-103">Applies To</span></span>  
  
-   <span data-ttu-id="079e6-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="079e6-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="079e6-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="079e6-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="079e6-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="079e6-106">Overview</span></span>  
 <span data-ttu-id="079e6-107">In diesem Thema wird beschrieben, wie Sie Ansprüche unterstützende WCF-Dienste mithilfe von WIF erstellen.</span><span class="sxs-lookup"><span data-stu-id="079e6-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="079e6-108">In einem Ansprüche unterstützenden Webdienstszenario sind normalerweise drei Parteien beteiligt: der Webdienst selbst, der Endbenutzer und der Sicherheitstokendienst (STS).</span><span class="sxs-lookup"><span data-stu-id="079e6-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="079e6-109">Die folgende Abbildung beschreibt dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="079e6-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="079e6-110">![WIF Basic Claims Aware WCF Service (WIF grundlegende, Ansprüche unterstützende WCF-Dienste)](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="079e6-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="079e6-111">Der WCF-Dienstclient (mitunter auch als Agent bezeichnet) verwendet WIF, um Anmeldeinformationen an den STS zu senden. Nach erfolgreicher Authentifizierung gibt der STS ein Token für den Agent aus.</span><span class="sxs-lookup"><span data-stu-id="079e6-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="079e6-112">Der Agent sendet dieses vom STS ausgegebene Token an den WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="079e6-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="079e6-113">Der Ansprüche unterstützende WCF-Dienst wird so konfiguriert, dass er dem STS und den Token, die er ausgibt, vertraut.</span><span class="sxs-lookup"><span data-stu-id="079e6-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="079e6-114">Der Ansprüche unterstützende WCF-Dienst verwendet WIF, um das Token zu überprüfen und zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="079e6-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="079e6-115">Entwickler verwenden die entsprechende WIF-API und -Typen wie **ClaimsPrincipal** für die Anforderungen der Anwendung, z.B. das Implementieren der entsprechenden Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="079e6-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="079e6-116">Ab .NET 4.5 ist WIF Bestandteil von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="079e6-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="079e6-117">Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="079e6-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="079e6-118">Mit WIF 4.5 müssen keine Out-of-Band-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="079e6-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="079e6-119">WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="079e6-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="079e6-120">STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="079e6-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="079e6-121">Microsoft bietet zwei STS-Dienste nach Industriestandard an:</span><span class="sxs-lookup"><span data-stu-id="079e6-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="079e6-122">[Active Directory-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="079e6-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="079e6-123">[Windows Azure-Zugriffssteuerungsdienst (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="079e6-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="079e6-124">AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="079e6-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="079e6-125">Azure Active Directory Access Control (auch bekannt als Access Control Service oder ACS) ist ein Clouddienst, der als Bestandteil von Microsoft Azure angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="079e6-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="079e6-126">Zu Test- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="079e6-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="079e6-127">Beispielsweise können Sie den lokalen Entwicklungs-STS verwenden, der Teil des [Identitäts- und Zugriffs-Tools für Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) ist, welches kostenlos online erhältlich ist.</span><span class="sxs-lookup"><span data-stu-id="079e6-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="079e6-128">Zum Erstellen Ihres ersten Ansprüche unterstützenden WCF-Diensts mithilfe von WIF finden Sie unter [Vorgehensweise: Aktivieren von WIF für eine WCF-Webdienstanwendung](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="079e6-128">To build your first claims-aware WCF service using WIF, see [How To: Enable WIF for a WCF Web Service Application](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="079e6-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="079e6-129">See Also</span></span>  
 [<span data-ttu-id="079e6-130">Erste Schritte mit WIF</span><span class="sxs-lookup"><span data-stu-id="079e6-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
