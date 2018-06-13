---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 097112a8b54467843554047882e55b62d7813c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352876"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="3bb06-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="3bb06-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="3bb06-103">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse, die dem Host Windows Communication Foundation (WCF)-Dienste, und Verbindungszugriff auf den Freigabedienst angeben.</span><span class="sxs-lookup"><span data-stu-id="3bb06-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="3bb06-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="3bb06-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb06-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bb06-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bb06-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb06-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3bb06-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3bb06-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bb06-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3bb06-108">Attributes</span></span>  
 <span data-ttu-id="3bb06-109">Keine</span><span class="sxs-lookup"><span data-stu-id="3bb06-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3bb06-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb06-110">Child Elements</span></span>  
  
|<span data-ttu-id="3bb06-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="3bb06-111">Attribute</span></span>|<span data-ttu-id="3bb06-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bb06-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3bb06-113">\<add></span><span class="sxs-lookup"><span data-stu-id="3bb06-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="3bb06-114">Fügt ein Benutzerkonto für Prozesse, die WCF-Dienste hosten und Verbindungszugriff auf den Freigabedienst</span><span class="sxs-lookup"><span data-stu-id="3bb06-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3bb06-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3bb06-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3bb06-116">Element</span><span class="sxs-lookup"><span data-stu-id="3bb06-116">Element</span></span>|<span data-ttu-id="3bb06-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3bb06-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bb06-118">[\<NET.Pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oder [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="3bb06-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="3bb06-119">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="3bb06-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bb06-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bb06-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
