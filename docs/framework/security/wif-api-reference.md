---
title: WIF-API-Verweis
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
ms.openlocfilehash: c94ccd3f25be576c57fda798c6b2b8cc25357022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172210"
---
# <a name="wif-api-reference"></a><span data-ttu-id="8ef82-102">WIF-API-Verweis</span><span class="sxs-lookup"><span data-stu-id="8ef82-102">WIF API Reference</span></span>
<span data-ttu-id="8ef82-103">Windows Identity Foundation-Klassen (WIF) werden in folgende Assemblys unterteilt: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) und `System.ServiceModel` (System.ServiceModel.dll).</span><span class="sxs-lookup"><span data-stu-id="8ef82-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="8ef82-104">Dieses Thema enthält Links zu den WIF-Namespaces und kurze Erläuterungen zu den Klassen, die jeder Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="8ef82-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ef82-105">In den folgenden `System.IdentityModel`-Namespaces sind Klassen enthalten, die das anspruchsbasierte WCF-Identitätsmodell implementieren: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> und <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ef82-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8ef82-106">Beginnend mit .NET Framework 4.5: Das anspruchsbasierte WCF-Identitätsmodell wird von WIF abgelöst.</span><span class="sxs-lookup"><span data-stu-id="8ef82-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="8ef82-107">Sie sollten beim Erstellen von Projektmappen auf Grundlage von WIF in diesen drei Namespaces keine Klassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ef82-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-108">Enthält Klassen, die Cookietransformationen, Sicherheitstokendienste und spezielle XML-Wörterbuch-Reader darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-109">Enthält Klassen, die Konfigurationen für Anwendungen und Dienste erstellen, die mit der Windows Identity Foundation (WIF) erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8ef82-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="8ef82-110">Die Klassen in diesem Namespace stellen Einstellungen unter dem [\<IdentityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)-Element dar.</span><span class="sxs-lookup"><span data-stu-id="8ef82-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-111">Enthält Klassen, die Elemente in einem Verbundmetadatendokument darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-112">Enthält Klassen, die WS-Trust-Elemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-113">Enthält Klassen, die in den passiven (WS-Verbund)-Szenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ef82-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="8ef82-114">Enthält außerdem einige Klassen, die Einstellungen unter dem [\<System.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)-Element darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="8ef82-115">Einstellungen unter diesem Element konfigurieren WS-Verbund für Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="8ef82-116">Der `System.IdentityModel.Services.Configuration`-Namespace enthält die meisten Klassen, mit denen der WS-Verbund konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8ef82-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-117">Enthält Klassen, die WIF-Anwendungen, die das WS-Verbundprotokoll verwenden, konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ef82-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="8ef82-118">Die Klassen in diesem Namespace stellen die Einstellungen unter dem [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)-Element dar.</span><span class="sxs-lookup"><span data-stu-id="8ef82-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="8ef82-119">Der `System.IdentityModel.Services`-Namespace enthält auch einige Klassen, mit denen der WS-Verbund konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8ef82-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-120">Enthält spezialisierte Sicherheitstokenhandler für Webfarm-Szenarios.</span><span class="sxs-lookup"><span data-stu-id="8ef82-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-121">Enthält Klassen, die Sicherheitstoken, Sicherheitstokenhandler und andere Sicherheitstokenartefakte darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-122">Enthält Klassen, die Ansprüche, anspruchsbasierte Identitäten, anspruchsbasierte Prinzipale und andere anspruchsbasierte Identitätsmodellartefakte darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef82-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="8ef82-123">Enthält Klassen, die WCF-Verträge, Kanäle, Diensthosts und andere Artefakte darstellen, die in aktiven (WS-Trust)-Szenarios verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ef82-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="8ef82-124">Dieser Namespace enthält außerdem Klassen, die spezifisch für Windows Communication Foundation (WCF) sind und nicht von WIF verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ef82-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef82-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ef82-125">See also</span></span>

- [<span data-ttu-id="8ef82-126">Referenz zur WIF-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8ef82-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)
- [<span data-ttu-id="8ef82-127">Namespacezuordnung zwischen WIF 3.5 und WIF 4.5</span><span class="sxs-lookup"><span data-stu-id="8ef82-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
