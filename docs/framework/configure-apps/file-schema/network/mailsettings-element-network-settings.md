---
title: '&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 954755c7576e0ca4dd7946926c77e1e7e18055e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713953"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="b4629-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b4629-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b4629-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="b4629-103">Configures mail sending options.</span></span>  

<span data-ttu-id="b4629-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b4629-104">\<configuration></span></span>  
<span data-ttu-id="b4629-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b4629-105">\<system.net></span></span>  
<span data-ttu-id="b4629-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="b4629-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4629-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4629-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4629-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4629-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b4629-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4629-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4629-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4629-110">Attributes</span></span>  
 <span data-ttu-id="b4629-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b4629-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b4629-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4629-112">Child Elements</span></span>  
  
|<span data-ttu-id="b4629-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b4629-113">Attribute</span></span>|<span data-ttu-id="b4629-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4629-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b4629-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b4629-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="b4629-116">Konfiguriert die Optionen der Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="b4629-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4629-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4629-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b4629-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="b4629-118">**Element**</span></span>|<span data-ttu-id="b4629-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b4629-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b4629-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b4629-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b4629-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b4629-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4629-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4629-122">Example</span></span>  
 <span data-ttu-id="b4629-123">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b4629-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="b4629-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4629-124">See also</span></span>
- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="b4629-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b4629-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
