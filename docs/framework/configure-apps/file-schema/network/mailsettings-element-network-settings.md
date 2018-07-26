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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a9afd992a12392ae0ad1c27eea305cb7e367686d
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874415"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="e6a23-102">&lt;MailSettings&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a23-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e6a23-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="e6a23-103">Configures mail sending options.</span></span>  

<span data-ttu-id="e6a23-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e6a23-104">\<configuration></span></span>  
<span data-ttu-id="e6a23-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e6a23-105">\<system.net></span></span>  
<span data-ttu-id="e6a23-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="e6a23-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a23-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6a23-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6a23-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a23-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e6a23-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6a23-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6a23-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6a23-110">Attributes</span></span>  
 <span data-ttu-id="e6a23-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e6a23-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6a23-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a23-112">Child Elements</span></span>  
  
|<span data-ttu-id="e6a23-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6a23-113">Attribute</span></span>|<span data-ttu-id="e6a23-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6a23-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e6a23-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a23-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="e6a23-116">Konfiguriert die Optionen der Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="e6a23-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6a23-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6a23-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e6a23-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="e6a23-118">**Element**</span></span>|<span data-ttu-id="e6a23-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e6a23-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e6a23-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a23-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="e6a23-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e6a23-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6a23-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6a23-122">Example</span></span>  
 <span data-ttu-id="e6a23-123">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e6a23-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6a23-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6a23-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="e6a23-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e6a23-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
