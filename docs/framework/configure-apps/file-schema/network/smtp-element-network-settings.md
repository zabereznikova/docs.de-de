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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089098"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="734f0-102">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="734f0-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="734f0-103">Konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="734f0-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="734f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="734f0-104">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="734f0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="734f0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="734f0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="734f0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="734f0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="734f0-107">Attributes</span></span>  
  
|<span data-ttu-id="734f0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="734f0-108">Attribute</span></span>|<span data-ttu-id="734f0-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="734f0-109">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="734f0-110">Gibt das Übermittlungs Format für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="734f0-110">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="734f0-111">Zulässige Werte sind "SevenBit" und "International".</span><span class="sxs-lookup"><span data-stu-id="734f0-111">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="734f0-112">Gibt die Übermittlungs Methode für e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="734f0-112">Specifies the delivery method for emails.</span></span> <span data-ttu-id="734f0-113">Zulässige Werte sind Network, pickupdirectoriyfromiis und SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="734f0-113">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="734f0-114">Gibt die from-Adresse für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="734f0-114">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="734f0-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="734f0-115">Child Elements</span></span>  
  
|<span data-ttu-id="734f0-116">attribute</span><span class="sxs-lookup"><span data-stu-id="734f0-116">Attribute</span></span>|<span data-ttu-id="734f0-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="734f0-117">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="734f0-118">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="734f0-118">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="734f0-119">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="734f0-119">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="734f0-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="734f0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="734f0-121">**Element**</span><span class="sxs-lookup"><span data-stu-id="734f0-121">**Element**</span></span>|<span data-ttu-id="734f0-122">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="734f0-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="734f0-123">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="734f0-123">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="734f0-124">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="734f0-124">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="734f0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="734f0-125">Example</span></span>  
 <span data-ttu-id="734f0-126">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="734f0-126">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="734f0-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="734f0-127">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="734f0-128">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="734f0-128">Network Settings Schema</span></span>](index.md)
