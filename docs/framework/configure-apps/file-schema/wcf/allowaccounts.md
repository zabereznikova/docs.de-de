---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102621"
---
# <a name="allowaccounts"></a><span data-ttu-id="87f82-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="87f82-101">\<allowAccounts></span></span>
<span data-ttu-id="87f82-102">Enthält eine Auflistung von Konfigurationselementen, die angeben, Benutzerkonten für Prozesse, die dem Host Windows Communication Foundation (WCF)-Dienste, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="87f82-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="87f82-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="87f82-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87f82-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87f82-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87f82-105">Attributes and Elements</span></span>  
 <span data-ttu-id="87f82-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87f82-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87f82-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="87f82-107">Attributes</span></span>  
 <span data-ttu-id="87f82-108">Keine</span><span class="sxs-lookup"><span data-stu-id="87f82-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87f82-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f82-109">Child Elements</span></span>  
  
|<span data-ttu-id="87f82-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="87f82-110">Attribute</span></span>|<span data-ttu-id="87f82-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87f82-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="87f82-112">\<add></span><span class="sxs-lookup"><span data-stu-id="87f82-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="87f82-113">Fügt ein Benutzerkonto für Prozesse, die WCF-Dienste hosten, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde</span><span class="sxs-lookup"><span data-stu-id="87f82-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87f82-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87f82-114">Parent Elements</span></span>  
  
|<span data-ttu-id="87f82-115">Element</span><span class="sxs-lookup"><span data-stu-id="87f82-115">Element</span></span>|<span data-ttu-id="87f82-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87f82-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87f82-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="87f82-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="87f82-118">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="87f82-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87f82-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87f82-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
