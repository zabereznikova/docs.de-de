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
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089098"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="68929-102">\<SMTP->-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="68929-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="68929-103">Konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="68929-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
<span data-ttu-id="68929-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="68929-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="68929-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="68929-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="68929-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="68929-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="68929-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<SMTP->**</span><span class="sxs-lookup"><span data-stu-id="68929-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="68929-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="68929-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68929-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68929-109">Attributes and Elements</span></span>  
 <span data-ttu-id="68929-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68929-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68929-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="68929-111">Attributes</span></span>  
  
|<span data-ttu-id="68929-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="68929-112">Attribute</span></span>|<span data-ttu-id="68929-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68929-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="68929-114">Gibt das Übermittlungs Format für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="68929-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="68929-115">Zulässige Werte sind "SevenBit" und "International".</span><span class="sxs-lookup"><span data-stu-id="68929-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="68929-116">Gibt die Übermittlungs Methode für e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="68929-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="68929-117">Zulässige Werte sind Network, pickupdirectoriyfromiis und SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="68929-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="68929-118">Gibt die from-Adresse für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="68929-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68929-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68929-119">Child Elements</span></span>  
  
|<span data-ttu-id="68929-120">Attribut</span><span class="sxs-lookup"><span data-stu-id="68929-120">Attribute</span></span>|<span data-ttu-id="68929-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68929-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="68929-122">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="68929-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="68929-123">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="68929-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68929-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68929-124">Parent Elements</span></span>  
  
|<span data-ttu-id="68929-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="68929-125">**Element**</span></span>|<span data-ttu-id="68929-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="68929-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="68929-127">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="68929-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="68929-128">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="68929-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="68929-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68929-129">Example</span></span>  
 <span data-ttu-id="68929-130">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="68929-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68929-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68929-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="68929-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="68929-132">Network Settings Schema</span></span>](index.md)
