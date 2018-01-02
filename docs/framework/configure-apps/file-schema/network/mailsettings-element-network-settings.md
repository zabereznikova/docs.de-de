---
title: '&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 5ae9ecdfa9cccb7c70c153153b921151aad50e7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="4a9fb-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4a9fb-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="4a9fb-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="4a9fb-103">Configures mail sending options.</span></span>  

<span data-ttu-id="4a9fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4a9fb-104">\<configuration></span></span>  
<span data-ttu-id="4a9fb-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="4a9fb-105">\<system.net></span></span>  
<span data-ttu-id="4a9fb-106">\<MailSettings ></span><span class="sxs-lookup"><span data-stu-id="4a9fb-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9fb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a9fb-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a9fb-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4a9fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4a9fb-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a9fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a9fb-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4a9fb-110">Attributes</span></span>  
 <span data-ttu-id="4a9fb-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4a9fb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4a9fb-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a9fb-112">Child Elements</span></span>  
  
|<span data-ttu-id="4a9fb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4a9fb-113">Attribute</span></span>|<span data-ttu-id="4a9fb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a9fb-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4a9fb-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4a9fb-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="4a9fb-116">Konfiguriert die Simple Mail Transport Protocol-Optionen.</span><span class="sxs-lookup"><span data-stu-id="4a9fb-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a9fb-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4a9fb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4a9fb-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="4a9fb-118">**Element**</span></span>|<span data-ttu-id="4a9fb-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4a9fb-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4a9fb-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4a9fb-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="4a9fb-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4a9fb-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4a9fb-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4a9fb-122">Example</span></span>  
 <span data-ttu-id="4a9fb-123">Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mails unter Verwendung der Standard-Netzwerkanmeldeinformationen zu senden.</span><span class="sxs-lookup"><span data-stu-id="4a9fb-123">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a9fb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a9fb-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="4a9fb-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="4a9fb-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
