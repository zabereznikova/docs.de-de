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
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697606"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="30ef8-102">\<smtp >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="30ef8-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="30ef8-103">Konfiguriert das Übermittlungs Format, die Übermittlungs Methode und die Absenderadresse für das Senden von e-Mails.</span><span class="sxs-lookup"><span data-stu-id="30ef8-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="30ef8-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="30ef8-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="30ef8-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30ef8-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="30ef8-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailsettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="30ef8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="30ef8-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="30ef8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ef8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="30ef8-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30ef8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30ef8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30ef8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30ef8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30ef8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="30ef8-111">Attributes</span></span>  
  
|<span data-ttu-id="30ef8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="30ef8-112">Attribute</span></span>|<span data-ttu-id="30ef8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30ef8-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="30ef8-114">Gibt das Übermittlungs Format für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="30ef8-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="30ef8-115">Zulässige Werte sind "SevenBit" und "International".</span><span class="sxs-lookup"><span data-stu-id="30ef8-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="30ef8-116">Gibt die Übermittlungs Methode für e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="30ef8-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="30ef8-117">Zulässige Werte sind Network, pickupdirectoriyfromiis und SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="30ef8-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="30ef8-118">Gibt die from-Adresse für ausgehende e-Mails an.</span><span class="sxs-lookup"><span data-stu-id="30ef8-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30ef8-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30ef8-119">Child Elements</span></span>  
  
|<span data-ttu-id="30ef8-120">Attribut</span><span class="sxs-lookup"><span data-stu-id="30ef8-120">Attribute</span></span>|<span data-ttu-id="30ef8-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30ef8-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="30ef8-122">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="30ef8-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="30ef8-123">Konfiguriert die Netzwerkoptionen für einen externen SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="30ef8-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30ef8-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30ef8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="30ef8-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="30ef8-125">**Element**</span></span>|<span data-ttu-id="30ef8-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="30ef8-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="30ef8-127">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="30ef8-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="30ef8-128">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="30ef8-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30ef8-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30ef8-129">Example</span></span>  
 <span data-ttu-id="30ef8-130">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="30ef8-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="30ef8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30ef8-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="30ef8-132">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="30ef8-132">Network Settings Schema</span></span>](index.md)
