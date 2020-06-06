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
ms.openlocfilehash: 4e8bf23ce39edadf80f019315c690b597b3d7361
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089234"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="9f301-102">\<mailSettings>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9f301-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="9f301-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="9f301-103">Configures mail sending options.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<mailSettings>**

## <a name="syntax"></a><span data-ttu-id="9f301-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f301-104">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f301-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f301-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9f301-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f301-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f301-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f301-107">Attributes</span></span>  
 <span data-ttu-id="9f301-108">Keine</span><span class="sxs-lookup"><span data-stu-id="9f301-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f301-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f301-109">Child Elements</span></span>  
  
|<span data-ttu-id="9f301-110">attribute</span><span class="sxs-lookup"><span data-stu-id="9f301-110">Attribute</span></span>|<span data-ttu-id="9f301-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f301-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="9f301-112">\<smtp>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9f301-112">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="9f301-113">Konfiguriert die Optionen des Simple Mail-Transport Protokolls.</span><span class="sxs-lookup"><span data-stu-id="9f301-113">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f301-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f301-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9f301-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="9f301-115">**Element**</span></span>|<span data-ttu-id="9f301-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f301-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9f301-117">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9f301-117">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="9f301-118">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f301-118">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9f301-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f301-119">Example</span></span>  
 <span data-ttu-id="9f301-120">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="9f301-120">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9f301-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f301-121">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="9f301-122">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="9f301-122">Network Settings Schema</span></span>](index.md)
