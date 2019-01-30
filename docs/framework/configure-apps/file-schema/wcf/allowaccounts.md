---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: fd3121146577122446ba82528fc6e46dadbf5033
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255548"
---
# <a name="allowaccounts"></a><span data-ttu-id="d4451-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="d4451-101">\<allowAccounts></span></span>
<span data-ttu-id="d4451-102">Enthält eine Auflistung von Konfigurationselementen, die angeben, Benutzerkonten für Prozesse, die dem Host Windows Communication Foundation (WCF)-Dienste, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="d4451-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="d4451-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="d4451-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4451-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4451-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4451-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d4451-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d4451-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d4451-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4451-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4451-107">Attributes</span></span>  
 <span data-ttu-id="d4451-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d4451-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4451-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4451-109">Child Elements</span></span>  
  
|<span data-ttu-id="d4451-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d4451-110">Attribute</span></span>|<span data-ttu-id="d4451-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4451-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d4451-112">\<add></span><span class="sxs-lookup"><span data-stu-id="d4451-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="d4451-113">Fügt ein Benutzerkonto für Prozesse, die WCF-Dienste hosten, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde</span><span class="sxs-lookup"><span data-stu-id="d4451-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4451-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4451-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d4451-115">Element</span><span class="sxs-lookup"><span data-stu-id="d4451-115">Element</span></span>|<span data-ttu-id="d4451-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4451-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4451-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="d4451-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="d4451-118">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="d4451-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4451-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4451-119">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
