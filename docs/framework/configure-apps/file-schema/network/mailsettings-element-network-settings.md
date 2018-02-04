---
title: '&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: ce7ec8bea57436ebd184cf0d593870999405f72f
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="7f189-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7f189-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="7f189-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="7f189-103">Configures mail sending options.</span></span>  

<span data-ttu-id="7f189-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7f189-104">\<configuration></span></span>  
<span data-ttu-id="7f189-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7f189-105">\<system.net></span></span>  
<span data-ttu-id="7f189-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="7f189-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f189-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f189-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f189-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7f189-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f189-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f189-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f189-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7f189-110">Attributes</span></span>  
 <span data-ttu-id="7f189-111">Keine</span><span class="sxs-lookup"><span data-stu-id="7f189-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f189-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f189-112">Child Elements</span></span>  
  
|<span data-ttu-id="7f189-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7f189-113">Attribute</span></span>|<span data-ttu-id="7f189-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f189-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7f189-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7f189-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="7f189-116">Konfiguriert die Simple Mail Transport Protocol-Optionen.</span><span class="sxs-lookup"><span data-stu-id="7f189-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f189-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7f189-117">Parent Elements</span></span>  
  
|<span data-ttu-id="7f189-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="7f189-118">**Element**</span></span>|<span data-ttu-id="7f189-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7f189-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7f189-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7f189-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="7f189-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7f189-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f189-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f189-122">Example</span></span>  
 <span data-ttu-id="7f189-123">Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mail-Nachricht mit der Standard-Netzwerkanmeldeinformationen zu senden.</span><span class="sxs-lookup"><span data-stu-id="7f189-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f189-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f189-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="7f189-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7f189-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
