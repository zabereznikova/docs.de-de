---
title: "WCF und internationale Domänennamen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cae287ab440115b15f6c26209a3d40bee4f9703b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="e4d39-102">WCF und internationale Domänennamen</span><span class="sxs-lookup"><span data-stu-id="e4d39-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="e4d39-103">Unterstützung für WCF-Dienste mit internationalisierten Domänennamen (Internationalized Domain Names, IDNs) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e4d39-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="e4d39-104">Ein internationalisierter Domänenname ist ein Domänenname, der Nicht-ASCII-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="e4d39-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="e4d39-105">Diese Unterstützung umfasst die Fähigkeit zum Hosten eines WCF-Diensts mit einem IDN und zum Kommunizieren eines WCF-Clients mit einem Webdienst, der über einen IDN verfügt.</span><span class="sxs-lookup"><span data-stu-id="e4d39-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="e4d39-106">System.Uri und IDN</span><span class="sxs-lookup"><span data-stu-id="e4d39-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="e4d39-107"><xref:System.Uri> verfügt über die beiden Eigenschaften <xref:System.Uri.Host%2A> und <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4d39-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="e4d39-108">Diese Eigenschaften enthalten abhängig von den IDN-Konfigurationseinstellungen Unicode- oder Punycode-Werte.</span><span class="sxs-lookup"><span data-stu-id="e4d39-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="e4d39-109">IDN wird in der Konfigurationsdatei einer Anwendung mit dem folgenden XML-Code aktiviert:</span><span class="sxs-lookup"><span data-stu-id="e4d39-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="e4d39-110">Die \<Idn >-Element enthält das aktivierte Attribut, das auf einen der folgenden Werte festgelegt werden kann:</span><span class="sxs-lookup"><span data-stu-id="e4d39-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="e4d39-111">"None"</span><span class="sxs-lookup"><span data-stu-id="e4d39-111">"None"</span></span>  
  
2.  <span data-ttu-id="e4d39-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="e4d39-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="e4d39-113">"Alle"</span><span class="sxs-lookup"><span data-stu-id="e4d39-113">"All"</span></span>  
  
 <span data-ttu-id="e4d39-114">Wenn die IDN-Einstellung auf "None" festgelegt ist, werden keine Konvertierungen von Uri.Host oder Uri.DnsSafeHost ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4d39-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="e4d39-115">Wenn die IDN-Einstellung auf "Alle", Uri festgelegt wird. Host bleibt Unicode- und Uri. DnsSafeHost werden in Punycode konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e4d39-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="e4d39-116">Wenn die IDN-Einstellung auf "AllExceptIntranet", Uri festgelegt ist. DnsSafeHost für Internetadressen in Punycode konvertiert, und Unicode für Intranetadressen verbleiben.</span><span class="sxs-lookup"><span data-stu-id="e4d39-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="e4d39-117">Diese Einstellung ist für eine ordnungsgemäße DNS-Namensauflösung wichtig.</span><span class="sxs-lookup"><span data-stu-id="e4d39-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="e4d39-118">Beachten Sie, dass diese Einstellung für Windows 8 und spätere Versionen nicht konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e4d39-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e4d39-119">Sie sollten eine Adresse nie mit Punycode hartcodieren.</span><span class="sxs-lookup"><span data-stu-id="e4d39-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="e4d39-120">WCF konvertiert sie auf Grundlage der verwendeten Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e4d39-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e4d39-121">Wenn Sie applicationHost.exe.config Unicode-Zeichen hinzufügen, speichern Sie die Datei mit UTF-8-Codierung.</span><span class="sxs-lookup"><span data-stu-id="e4d39-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d39-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4d39-122">See Also</span></span>  
 [<span data-ttu-id="e4d39-123">System.Uri</span><span class="sxs-lookup"><span data-stu-id="e4d39-123">System.Uri</span></span>](http://msdn.microsoft.com/library/system.uri.aspx)
