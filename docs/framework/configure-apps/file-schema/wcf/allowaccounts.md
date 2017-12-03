---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20d411fbe052940fd8fc752e74d012f28ffa441b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="4e8ab-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="4e8ab-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="4e8ab-103">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="4e8ab-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="4e8ab-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="4e8ab-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8ab-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e8ab-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e8ab-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4e8ab-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4e8ab-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e8ab-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e8ab-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="4e8ab-108">Attributes</span></span>  
 <span data-ttu-id="4e8ab-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="4e8ab-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e8ab-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e8ab-110">Child Elements</span></span>  
  
|<span data-ttu-id="4e8ab-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4e8ab-111">Attribute</span></span>|<span data-ttu-id="4e8ab-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e8ab-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4e8ab-113">\<add></span><span class="sxs-lookup"><span data-stu-id="4e8ab-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="4e8ab-114">Fügt ein Benutzerkonto für Prozesse hinzu, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="4e8ab-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e8ab-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4e8ab-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4e8ab-116">Element</span><span class="sxs-lookup"><span data-stu-id="4e8ab-116">Element</span></span>|<span data-ttu-id="4e8ab-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e8ab-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e8ab-118">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oder [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="4e8ab-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="4e8ab-119">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="4e8ab-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e8ab-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e8ab-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
