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
ms.openlocfilehash: 5c7b4d8fae2774fe8e52718fbce91e4bc193c124
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198431"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="5db29-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5db29-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="5db29-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="5db29-103">Configures mail sending options.</span></span>  

<span data-ttu-id="5db29-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5db29-104">\<configuration></span></span>  
<span data-ttu-id="5db29-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5db29-105">\<system.net></span></span>  
<span data-ttu-id="5db29-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="5db29-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db29-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5db29-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5db29-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5db29-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5db29-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5db29-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5db29-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5db29-110">Attributes</span></span>  
 <span data-ttu-id="5db29-111">Keine</span><span class="sxs-lookup"><span data-stu-id="5db29-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5db29-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5db29-112">Child Elements</span></span>  
  
|<span data-ttu-id="5db29-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="5db29-113">Attribute</span></span>|<span data-ttu-id="5db29-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5db29-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5db29-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5db29-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="5db29-116">Konfiguriert die Optionen der Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="5db29-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5db29-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5db29-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5db29-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="5db29-118">**Element**</span></span>|<span data-ttu-id="5db29-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5db29-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5db29-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5db29-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="5db29-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5db29-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5db29-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5db29-122">Example</span></span>  
 <span data-ttu-id="5db29-123">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5db29-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5db29-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5db29-124">See Also</span></span>  
- <xref:System.Net.Mail.SmtpClient>  
- [<span data-ttu-id="5db29-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5db29-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
