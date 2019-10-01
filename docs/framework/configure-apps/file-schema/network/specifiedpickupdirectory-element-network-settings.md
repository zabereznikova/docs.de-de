---
title: <specifiedPickupDirectory>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697591"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="7195a-102">\<specifiedpickupdirectory >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7195a-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="7195a-103">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="7195a-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="7195a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="7195a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="7195a-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7195a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="7195a-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailsettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7195a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="7195a-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7195a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="7195a-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<specifiedpickupdirectory >**</span><span class="sxs-lookup"><span data-stu-id="7195a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7195a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7195a-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7195a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7195a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7195a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7195a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7195a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7195a-112">Attributes</span></span>  
  
|<span data-ttu-id="7195a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7195a-113">Attribute</span></span>|<span data-ttu-id="7195a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7195a-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="7195a-115">Das Verzeichnis, in dem Anwendungen e-Mails zur späteren Verarbeitung durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="7195a-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7195a-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7195a-116">Child Elements</span></span>  
 <span data-ttu-id="7195a-117">Keine</span><span class="sxs-lookup"><span data-stu-id="7195a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7195a-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7195a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7195a-119">Element</span><span class="sxs-lookup"><span data-stu-id="7195a-119">Element</span></span>|<span data-ttu-id="7195a-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7195a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7195a-121">\<SMTP-> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7195a-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="7195a-122">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="7195a-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7195a-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7195a-123">Remarks</span></span>  
 <span data-ttu-id="7195a-124">Das `specifiedPickupDirectory`-Attribut legt das Verzeichnis fest, in dem Anwendungen e-Mail-Nachrichten zum Verarbeiten durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="7195a-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7195a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7195a-125">Example</span></span>  
 <span data-ttu-id="7195a-126">Im folgenden Beispiel wird c:\maildrop als e-Mail-Abhol Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="7195a-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7195a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7195a-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="7195a-128">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7195a-128">Network Settings Schema</span></span>](index.md)
