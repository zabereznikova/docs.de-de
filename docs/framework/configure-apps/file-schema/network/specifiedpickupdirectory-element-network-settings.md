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
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154607"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="86731-102">\<specifiedPickupDirectory> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="86731-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="86731-103">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="86731-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="86731-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86731-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86731-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="86731-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="86731-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="86731-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="86731-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="86731-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="86731-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span><span class="sxs-lookup"><span data-stu-id="86731-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86731-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="86731-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86731-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86731-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86731-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86731-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86731-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="86731-112">Attributes</span></span>  
  
|<span data-ttu-id="86731-113">attribute</span><span class="sxs-lookup"><span data-stu-id="86731-113">Attribute</span></span>|<span data-ttu-id="86731-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86731-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="86731-115">Das Verzeichnis, in dem Anwendungen E-Mails zur späteren Verarbeitung durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="86731-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86731-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86731-116">Child Elements</span></span>  
 <span data-ttu-id="86731-117">Keine.</span><span class="sxs-lookup"><span data-stu-id="86731-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86731-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86731-118">Parent Elements</span></span>  
  
|<span data-ttu-id="86731-119">Element</span><span class="sxs-lookup"><span data-stu-id="86731-119">Element</span></span>|<span data-ttu-id="86731-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86731-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86731-121">\<smtp> Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="86731-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="86731-122">Konfiguriert SMTP-E-Mail-Versandoptionen (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="86731-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86731-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="86731-123">Remarks</span></span>  
 <span data-ttu-id="86731-124">Das `specifiedPickupDirectory` Attribut legt das Verzeichnis fest, in dem Anwendungen E-Mail-Nachrichten speichern, die vom SMTP-Server verarbeitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="86731-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86731-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86731-125">Example</span></span>  
 <span data-ttu-id="86731-126">Im folgenden Beispiel wird c:-Maildrop als E-Mail-Abholverzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="86731-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86731-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86731-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="86731-128">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="86731-128">Network Settings Schema</span></span>](index.md)
