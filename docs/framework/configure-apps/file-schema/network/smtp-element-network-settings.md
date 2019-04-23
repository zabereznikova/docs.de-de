---
title: <smtp>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 1b5f7406f995a86f0a192dbf3249c067dff570ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140373"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="ba697-102">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba697-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="ba697-103">Konfiguriert das übermittlungsformat, die Übermittlungsmethode und die Absenderadresse zum Senden von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="ba697-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="ba697-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba697-104">\<configuration></span></span>  
<span data-ttu-id="ba697-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ba697-105">\<system.net></span></span>  
<span data-ttu-id="ba697-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="ba697-106">\<mailSettings></span></span>  
<span data-ttu-id="ba697-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="ba697-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba697-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba697-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba697-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba697-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba697-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba697-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba697-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba697-111">Attributes</span></span>  
  
|<span data-ttu-id="ba697-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba697-112">Attribute</span></span>|<span data-ttu-id="ba697-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba697-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="ba697-114">Gibt das übermittlungsformat für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="ba697-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="ba697-115">Zulässige Werte sind "SevenBit" und "International".</span><span class="sxs-lookup"><span data-stu-id="ba697-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="ba697-116">Gibt die Übermittlungsmethode für e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="ba697-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="ba697-117">Zulässige Werte sind, Netzwerk, PickupDirectoryFromIis und "specifiedPickupDirectory".</span><span class="sxs-lookup"><span data-stu-id="ba697-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="ba697-118">Gibt an, die Absenderadresse für ausgehende e-Mails.</span><span class="sxs-lookup"><span data-stu-id="ba697-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba697-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba697-119">Child Elements</span></span>  
  
|<span data-ttu-id="ba697-120">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba697-120">Attribute</span></span>|<span data-ttu-id="ba697-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba697-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="ba697-122">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="ba697-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="ba697-123">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="ba697-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba697-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba697-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba697-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="ba697-125">**Element**</span></span>|<span data-ttu-id="ba697-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ba697-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ba697-127">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba697-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="ba697-128">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="ba697-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ba697-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba697-129">Example</span></span>  
 <span data-ttu-id="ba697-130">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ba697-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="ba697-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba697-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="ba697-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ba697-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
