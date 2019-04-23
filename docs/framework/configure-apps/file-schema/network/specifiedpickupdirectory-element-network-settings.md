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
ms.openlocfilehash: a459fee557285935c383dcfaf512c8a8a9aea570
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099273"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="e7f80-102">\<"specifiedPickupDirectory" >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e7f80-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="e7f80-103">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="e7f80-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="e7f80-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e7f80-104">\<configuration></span></span>  
<span data-ttu-id="e7f80-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e7f80-105">\<system.net></span></span>  
<span data-ttu-id="e7f80-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="e7f80-106">\<mailSettings></span></span>  
<span data-ttu-id="e7f80-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="e7f80-107">\<smtp></span></span>  
<span data-ttu-id="e7f80-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="e7f80-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f80-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7f80-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f80-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f80-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f80-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7f80-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f80-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e7f80-112">Attributes</span></span>  
  
|<span data-ttu-id="e7f80-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e7f80-113">Attribute</span></span>|<span data-ttu-id="e7f80-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7f80-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="e7f80-115">Das Verzeichnis, in dem Anwendungen für e-Mail-Adresse, zur späteren Verarbeitung durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="e7f80-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f80-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f80-116">Child Elements</span></span>  
 <span data-ttu-id="e7f80-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e7f80-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f80-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e7f80-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f80-119">Element</span><span class="sxs-lookup"><span data-stu-id="e7f80-119">Element</span></span>|<span data-ttu-id="e7f80-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7f80-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7f80-121">\<SMTP >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e7f80-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="e7f80-122">Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="e7f80-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f80-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7f80-123">Remarks</span></span>  
 <span data-ttu-id="e7f80-124">Die `specifiedPickupDirectory` Attribut legt das Verzeichnis, in dem Anwendungen vom SMTP-Server zu verarbeitende e-Mail-Nachrichten speichern.</span><span class="sxs-lookup"><span data-stu-id="e7f80-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7f80-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7f80-125">Example</span></span>  
 <span data-ttu-id="e7f80-126">Im folgenden Beispiel wird die c:\maildrop als e-Mail-pickup-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e7f80-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e7f80-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7f80-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="e7f80-128">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e7f80-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
