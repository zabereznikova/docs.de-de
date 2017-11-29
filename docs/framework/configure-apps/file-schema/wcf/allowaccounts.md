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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="a7e58-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="a7e58-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="a7e58-103">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="a7e58-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="a7e58-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="a7e58-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e58-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7e58-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7e58-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7e58-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a7e58-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7e58-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7e58-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7e58-108">Attributes</span></span>  
 <span data-ttu-id="a7e58-109">Keine.</span><span class="sxs-lookup"><span data-stu-id="a7e58-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7e58-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7e58-110">Child Elements</span></span>  
  
|<span data-ttu-id="a7e58-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a7e58-111">Attribute</span></span>|<span data-ttu-id="a7e58-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7e58-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a7e58-113">\<add></span><span class="sxs-lookup"><span data-stu-id="a7e58-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="a7e58-114">Fügt ein Benutzerkonto für Prozesse hinzu, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.</span><span class="sxs-lookup"><span data-stu-id="a7e58-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7e58-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7e58-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a7e58-116">Element</span><span class="sxs-lookup"><span data-stu-id="a7e58-116">Element</span></span>|<span data-ttu-id="a7e58-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7e58-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7e58-118">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oder [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="a7e58-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="a7e58-119">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="a7e58-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7e58-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7e58-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
