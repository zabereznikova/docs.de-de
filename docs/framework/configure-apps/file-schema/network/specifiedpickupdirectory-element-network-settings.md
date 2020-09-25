---
title: <specifiedPickupDirectory>-Element (Netzwerkeinstellungen)
description: Das <specifiedPickupDirectory> Netzwerk Einstellungs Element konfiguriert das lokale Verzeichnis für eine SMTP-Server Option in der .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 5bb7fc5405b1ee2f0f054bc6e9f043a3f9fcd1ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176161"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="feba0-103">\<specifiedPickupDirectory>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="feba0-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>

<span data-ttu-id="feba0-104">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="feba0-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="feba0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="feba0-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="feba0-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="feba0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="feba0-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="feba0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="feba0-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="feba0-108">Attributes</span></span>  
  
|<span data-ttu-id="feba0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="feba0-109">Attribute</span></span>|<span data-ttu-id="feba0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="feba0-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="feba0-111">Das Verzeichnis, in dem Anwendungen e-Mails zur späteren Verarbeitung durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="feba0-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="feba0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="feba0-112">Child Elements</span></span>  

 <span data-ttu-id="feba0-113">Keine</span><span class="sxs-lookup"><span data-stu-id="feba0-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="feba0-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="feba0-114">Parent Elements</span></span>  
  
|<span data-ttu-id="feba0-115">Element</span><span class="sxs-lookup"><span data-stu-id="feba0-115">Element</span></span>|<span data-ttu-id="feba0-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="feba0-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="feba0-117">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="feba0-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="feba0-118">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="feba0-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="feba0-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="feba0-119">Remarks</span></span>  

 <span data-ttu-id="feba0-120">Das- `specifiedPickupDirectory` Attribut legt das Verzeichnis fest, in dem Anwendungen vom SMTP-Server zu verarbeitende e-Mail-Nachrichten speichern.</span><span class="sxs-lookup"><span data-stu-id="feba0-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feba0-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="feba0-121">Example</span></span>  

 <span data-ttu-id="feba0-122">Im folgenden Beispiel wird c:\maildrop als e-Mail-Abhol Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="feba0-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="feba0-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="feba0-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="feba0-124">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="feba0-124">Network Settings Schema</span></span>](index.md)
