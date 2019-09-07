---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398408"
---
# <a name="allowaccounts"></a><span data-ttu-id="cd0f9-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="cd0f9-101">\<allowAccounts></span></span>
<span data-ttu-id="cd0f9-102">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die Windows Communication Foundation (WCF)-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="cd0f9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cd0f9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cd0f9-104">&nbsp;&nbsp;[ **\<System. Service Model. Activation->** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="cd0f9-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="cd0f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NET. Pipe->** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="cd0f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="cd0f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<allowaccounts->**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0f9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd0f9-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd0f9-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cd0f9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd0f9-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd0f9-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cd0f9-110">Attributes</span></span>  
 <span data-ttu-id="cd0f9-111">Keine</span><span class="sxs-lookup"><span data-stu-id="cd0f9-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cd0f9-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd0f9-112">Child Elements</span></span>  
  
|<span data-ttu-id="cd0f9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="cd0f9-113">Attribute</span></span>|<span data-ttu-id="cd0f9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd0f9-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="cd0f9-115">\<add></span><span class="sxs-lookup"><span data-stu-id="cd0f9-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="cd0f9-116">Fügt ein Benutzerkonto für Prozesse hinzu, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd0f9-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cd0f9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cd0f9-118">Element</span><span class="sxs-lookup"><span data-stu-id="cd0f9-118">Element</span></span>|<span data-ttu-id="cd0f9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd0f9-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd0f9-120">["net. Pipe" > oder "net. TCP" > \<](net-pipe.md) [ \<](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="cd0f9-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="cd0f9-121">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd0f9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd0f9-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
