---
title: <mailSettings>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 0e71284e914dac2d28448f3d8bd4bdc7a9f6b325
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277614"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="b0a4a-102">\<MailSettings >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="b0a4a-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-103">Configures mail sending options.</span></span>  

<span data-ttu-id="b0a4a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0a4a-104">\<configuration></span></span>  
<span data-ttu-id="b0a4a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b0a4a-105">\<system.net></span></span>  
<span data-ttu-id="b0a4a-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="b0a4a-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a4a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0a4a-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a4a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a4a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b0a4a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a4a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0a4a-110">Attributes</span></span>  
 <span data-ttu-id="b0a4a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b0a4a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0a4a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a4a-112">Child Elements</span></span>  
  
|<span data-ttu-id="b0a4a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0a4a-113">Attribute</span></span>|<span data-ttu-id="b0a4a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0a4a-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="b0a4a-115">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="b0a4a-116">Konfiguriert die Optionen der Simple Mail Transport Protocol.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a4a-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0a4a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a4a-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="b0a4a-118">**Element**</span></span>|<span data-ttu-id="b0a4a-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b0a4a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b0a4a-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b0a4a-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b0a4a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b0a4a-122">Example</span></span>  
 <span data-ttu-id="b0a4a-123">Das folgende Beispiel gibt die entsprechenden SMTP-Parameter zum Senden von e-Mails, die über die Standardanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b0a4a-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0a4a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0a4a-124">See also</span></span>
- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="b0a4a-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b0a4a-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
