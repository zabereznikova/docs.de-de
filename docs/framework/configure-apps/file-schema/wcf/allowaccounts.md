---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c1c4630e6191dbbe02688a4e4a9db9e18b8d36d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508417"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="6ff1b-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="6ff1b-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="6ff1b-103">Enthält eine Auflistung von Konfigurationselementen, die angeben, Benutzerkonten für Prozesse, die dem Host Windows Communication Foundation (WCF)-Dienste, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="6ff1b-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="6ff1b-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="6ff1b-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff1b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ff1b-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ff1b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ff1b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6ff1b-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ff1b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ff1b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ff1b-108">Attributes</span></span>  
 <span data-ttu-id="6ff1b-109">Keine</span><span class="sxs-lookup"><span data-stu-id="6ff1b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ff1b-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ff1b-110">Child Elements</span></span>  
  
|<span data-ttu-id="6ff1b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6ff1b-111">Attribute</span></span>|<span data-ttu-id="6ff1b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ff1b-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="6ff1b-113">\<add></span><span class="sxs-lookup"><span data-stu-id="6ff1b-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="6ff1b-114">Fügt ein Benutzerkonto für Prozesse, die WCF-Dienste hosten, und denen Verbindungszugriff auf den Freigabedienst gewährt wurde</span><span class="sxs-lookup"><span data-stu-id="6ff1b-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ff1b-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ff1b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6ff1b-116">Element</span><span class="sxs-lookup"><span data-stu-id="6ff1b-116">Element</span></span>|<span data-ttu-id="6ff1b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ff1b-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ff1b-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="6ff1b-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="6ff1b-119">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="6ff1b-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ff1b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ff1b-120">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
