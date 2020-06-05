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
ms.sourcegitcommit: 0a798a7e9680e2d0a5a81a3eaa203870ea782883
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "79154607"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="e64ce-102">\<specifiedPickupDirectory>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e64ce-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="e64ce-103">Konfiguriert das lokale Verzeichnis für einen SMTP (Simple Mail Transport Protocol)-Server.</span><span class="sxs-lookup"><span data-stu-id="e64ce-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="e64ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e64ce-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e64ce-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e64ce-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e64ce-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e64ce-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e64ce-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e64ce-107">Attributes</span></span>  
  
|<span data-ttu-id="e64ce-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e64ce-108">Attribute</span></span>|<span data-ttu-id="e64ce-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e64ce-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="e64ce-110">Das Verzeichnis, in dem Anwendungen e-Mails zur späteren Verarbeitung durch den SMTP-Server speichern.</span><span class="sxs-lookup"><span data-stu-id="e64ce-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e64ce-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e64ce-111">Child Elements</span></span>  
 <span data-ttu-id="e64ce-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e64ce-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e64ce-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e64ce-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e64ce-114">Element</span><span class="sxs-lookup"><span data-stu-id="e64ce-114">Element</span></span>|<span data-ttu-id="e64ce-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e64ce-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e64ce-116">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e64ce-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="e64ce-117">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="e64ce-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e64ce-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e64ce-118">Remarks</span></span>  
 <span data-ttu-id="e64ce-119">Das- `specifiedPickupDirectory` Attribut legt das Verzeichnis fest, in dem Anwendungen vom SMTP-Server zu verarbeitende e-Mail-Nachrichten speichern.</span><span class="sxs-lookup"><span data-stu-id="e64ce-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e64ce-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e64ce-120">Example</span></span>  
 <span data-ttu-id="e64ce-121">Im folgenden Beispiel wird c:\maildrop als e-Mail-Abhol Verzeichnis angegeben.</span><span class="sxs-lookup"><span data-stu-id="e64ce-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e64ce-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e64ce-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="e64ce-123">Netzwerk Einstellungs Schema</span><span class="sxs-lookup"><span data-stu-id="e64ce-123">Network Settings Schema</span></span>](index.md)
