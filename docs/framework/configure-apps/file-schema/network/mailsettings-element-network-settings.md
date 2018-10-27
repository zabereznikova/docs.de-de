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
ms.openlocfilehash: e23b9e1fdf8a348d0d38575db8112b37c8dd9b69
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50048761"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="80623-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="80623-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="80623-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="80623-103">Configures mail sending options.</span></span>  

<span data-ttu-id="80623-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="80623-104">\<configuration></span></span>  
<span data-ttu-id="80623-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="80623-105">\<system.net></span></span>  
<span data-ttu-id="80623-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="80623-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80623-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="80623-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80623-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80623-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80623-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80623-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80623-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="80623-110">Attributes</span></span>  
 <span data-ttu-id="80623-111">Keine</span><span class="sxs-lookup"><span data-stu-id="80623-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80623-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80623-112">Child Elements</span></span>  
  
|<span data-ttu-id="80623-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="80623-113">Attribute</span></span>|<span data-ttu-id="80623-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80623-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="80623-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="80623-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="80623-116">Konfiguriert die Optionen der Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="80623-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80623-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80623-117">Parent Elements</span></span>  
  
|<span data-ttu-id="80623-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="80623-118">**Element**</span></span>|<span data-ttu-id="80623-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="80623-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="80623-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="80623-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="80623-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="80623-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80623-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80623-122">Example</span></span>  
 <span data-ttu-id="80623-123">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="80623-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80623-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80623-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="80623-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="80623-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
