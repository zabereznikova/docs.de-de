---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 3432d33c0cd65af03d2b1ac1302ca2c8ff3e0f43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201641"
---
# \<allowAccounts>

<span data-ttu-id="8874c-101">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die Windows Communication Foundation (WCF)-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="8874c-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="8874c-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="8874c-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8874c-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8874c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="8874c-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8874c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8874c-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="8874c-105">Attributes</span></span>  

 <span data-ttu-id="8874c-106">Keine</span><span class="sxs-lookup"><span data-stu-id="8874c-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8874c-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8874c-107">Child Elements</span></span>  
  
|<span data-ttu-id="8874c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8874c-108">Attribute</span></span>|<span data-ttu-id="8874c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8874c-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="8874c-110">Fügt ein Benutzerkonto für Prozesse hinzu, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="8874c-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8874c-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8874c-111">Parent Elements</span></span>  
  
|<span data-ttu-id="8874c-112">Element</span><span class="sxs-lookup"><span data-stu-id="8874c-112">Element</span></span>|<span data-ttu-id="8874c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8874c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8874c-114">[\<net.pipe>](net-pipe.md) oder [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="8874c-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="8874c-115">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="8874c-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8874c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8874c-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
