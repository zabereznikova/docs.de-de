---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926600"
---
# <a name="allowaccounts"></a><span data-ttu-id="d079a-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="d079a-101">\<allowAccounts></span></span>
<span data-ttu-id="d079a-102">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die Windows Communication Foundation (WCF)-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="d079a-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="d079a-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="d079a-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d079a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d079a-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d079a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d079a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d079a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d079a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d079a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d079a-107">Attributes</span></span>  
 <span data-ttu-id="d079a-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d079a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d079a-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d079a-109">Child Elements</span></span>  
  
|<span data-ttu-id="d079a-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d079a-110">Attribute</span></span>|<span data-ttu-id="d079a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d079a-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d079a-112">\<add></span><span class="sxs-lookup"><span data-stu-id="d079a-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="d079a-113">Fügt ein Benutzerkonto für Prozesse hinzu, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="d079a-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d079a-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d079a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="d079a-115">Element</span><span class="sxs-lookup"><span data-stu-id="d079a-115">Element</span></span>|<span data-ttu-id="d079a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d079a-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d079a-117">["net. Pipe" > oder "net. TCP" > \<](net-pipe.md) [ \<](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="d079a-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="d079a-118">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="d079a-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d079a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d079a-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
