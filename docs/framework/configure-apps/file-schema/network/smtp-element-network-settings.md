---
title: '&lt;SMTP&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56912e09d24fc83e93a91cc42b1d96dcc68210f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="a2a81-102">&lt;SMTP&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2a81-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="a2a81-103">Konfiguriert das übermittlungsformat, die Übermittlungsmethode und die Absenderadresse zum Senden von e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a2a81-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="a2a81-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a2a81-104">\<configuration></span></span>  
<span data-ttu-id="a2a81-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a2a81-105">\<system.net></span></span>  
<span data-ttu-id="a2a81-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="a2a81-106">\<mailSettings></span></span>  
<span data-ttu-id="a2a81-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="a2a81-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a81-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2a81-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2a81-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a2a81-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a2a81-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2a81-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2a81-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a2a81-111">Attributes</span></span>  
  
|<span data-ttu-id="a2a81-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2a81-112">Attribute</span></span>|<span data-ttu-id="a2a81-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2a81-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="a2a81-114">Gibt das übermittlungsformat für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="a2a81-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="a2a81-115">Zulässige Werte sind "SevenBit" und "International".</span><span class="sxs-lookup"><span data-stu-id="a2a81-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="a2a81-116">Gibt die Übermittlungsmethode für e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="a2a81-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="a2a81-117">Zulässige Werte sind "network", "pickupDirectoryFromIis" und "specifiedPickupDirectory".</span><span class="sxs-lookup"><span data-stu-id="a2a81-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="a2a81-118">Gibt die Absenderadresse für ausgehende e-Mails.</span><span class="sxs-lookup"><span data-stu-id="a2a81-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2a81-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2a81-119">Child Elements</span></span>  
  
|<span data-ttu-id="a2a81-120">Attribut</span><span class="sxs-lookup"><span data-stu-id="a2a81-120">Attribute</span></span>|<span data-ttu-id="a2a81-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2a81-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="a2a81-122">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="a2a81-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="a2a81-123">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="a2a81-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2a81-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a2a81-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a2a81-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="a2a81-125">**Element**</span></span>|<span data-ttu-id="a2a81-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a2a81-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a2a81-127">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2a81-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="a2a81-128">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="a2a81-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2a81-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2a81-129">Example</span></span>  
 <span data-ttu-id="a2a81-130">Im folgenden Beispiel wird die entsprechenden SMTP-Parameter, um e-Mail-Nachricht mit der Standard-Netzwerkanmeldeinformationen zu senden.</span><span class="sxs-lookup"><span data-stu-id="a2a81-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="a2a81-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a81-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="a2a81-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a2a81-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
