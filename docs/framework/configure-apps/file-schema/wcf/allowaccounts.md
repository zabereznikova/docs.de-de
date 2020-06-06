---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398408"
---
# \<allowAccounts>
<span data-ttu-id="797b1-101">Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die Windows Communication Foundation (WCF)-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="797b1-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="797b1-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="797b1-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="797b1-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="797b1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="797b1-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="797b1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="797b1-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="797b1-105">Attributes</span></span>  
 <span data-ttu-id="797b1-106">Keine</span><span class="sxs-lookup"><span data-stu-id="797b1-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="797b1-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="797b1-107">Child Elements</span></span>  
  
|<span data-ttu-id="797b1-108">attribute</span><span class="sxs-lookup"><span data-stu-id="797b1-108">Attribute</span></span>|<span data-ttu-id="797b1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="797b1-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="797b1-110">Fügt ein Benutzerkonto für Prozesse hinzu, die WCF-Dienste hosten und Verbindungs Zugriff auf den Freigabe Dienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="797b1-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="797b1-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="797b1-111">Parent Elements</span></span>  
  
|<span data-ttu-id="797b1-112">Element</span><span class="sxs-lookup"><span data-stu-id="797b1-112">Element</span></span>|<span data-ttu-id="797b1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="797b1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="797b1-114">[\<net.pipe>](net-pipe.md)noch[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="797b1-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="797b1-115">Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.</span><span class="sxs-lookup"><span data-stu-id="797b1-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="797b1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="797b1-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
