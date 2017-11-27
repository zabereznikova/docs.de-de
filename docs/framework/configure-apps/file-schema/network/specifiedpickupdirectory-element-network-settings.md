---
title: '&lt;"specifiedPickupDirectory"&gt; -Element (Netzwerkeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ffe34e6a811dd644b149a0fda12f1d1cd338c761
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="c1112-102">&lt;"specifiedPickupDirectory"&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1112-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="c1112-103">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="c1112-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="c1112-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c1112-104">\<configuration></span></span>  
<span data-ttu-id="c1112-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="c1112-105">\<system.net></span></span>  
<span data-ttu-id="c1112-106">\<MailSettings ></span><span class="sxs-lookup"><span data-stu-id="c1112-106">\<mailSettings></span></span>  
<span data-ttu-id="c1112-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="c1112-107">\<smtp></span></span>  
<span data-ttu-id="c1112-108">\<"specifiedPickupDirectory" ></span><span class="sxs-lookup"><span data-stu-id="c1112-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1112-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1112-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1112-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1112-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1112-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1112-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1112-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1112-112">Attributes</span></span>  
  
|<span data-ttu-id="c1112-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1112-113">Attribute</span></span>|<span data-ttu-id="c1112-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1112-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="c1112-115">Das Verzeichnis, in denen Anwendungen für e-Mail-Einstellungen für die spätere Verarbeitung vom SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="c1112-115">The directory where applications save e-mail for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1112-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1112-116">Child Elements</span></span>  
 <span data-ttu-id="c1112-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c1112-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1112-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1112-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c1112-119">Element</span><span class="sxs-lookup"><span data-stu-id="c1112-119">Element</span></span>|<span data-ttu-id="c1112-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1112-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1112-121">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1112-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="c1112-122">Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="c1112-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1112-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1112-123">Remarks</span></span>  
 <span data-ttu-id="c1112-124">Die `specifiedPickupDirectory` Attribut legt das Verzeichnis, in dem Speichern Anwendungen e-Mail-Nachrichten an den SMTP-Server verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c1112-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1112-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1112-125">Example</span></span>  
 <span data-ttu-id="c1112-126">Im folgenden Beispiel wird c:\maildrop als e-Mail-pickup-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c1112-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1112-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1112-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="c1112-128">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="c1112-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
