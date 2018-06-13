---
title: 'Gewusst wie: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung'
ms.date: 03/30/2017
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: aef2300ccde12ae224e373ca4e19b4d10b9b4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395017"
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="01abd-102">Gewusst wie: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="01abd-102">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="01abd-103">Das folgende Codebeispiel zeigt, wie Sie die Computerkonfigurationsdatei *machine.config* ändern, um die IPv6-Unterstützung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="01abd-103">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="01abd-104">Die Datei *machine.config* ist im Ordner *%Windir%\Microsoft.NET\Framework* in dem Verzeichnis gespeichert, in dem Windows installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="01abd-104">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="01abd-105">Es gibt für jede Version von .NET Framework, die auf dem Computer installiert ist, eine eigene Datei *machine.config* in den Unterordnern von *%Windir%\Microsoft.NET\Framework* (z.B. *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span><span class="sxs-lookup"><span data-stu-id="01abd-105">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="01abd-106">Diese Einstellungen können auch in der Konfigurationsdatei für die Anwendung vorgenommen werden. Die Anwendungskonfigurationsdatei hat Vorrang vor der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="01abd-106">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="01abd-107">Für .NET Framework Version 1.1 und früher gibt der Wert des Konfigurationsschalters **ipv6 enabled** an, ob Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-Adressen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="01abd-107">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="01abd-108">Für .NET Framework Version 2.0 und höher geben alle Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>-Methode), sofern Windows IPv6 unterstützt, IPv6-Adressen mit einer Einschränkung zurück.</span><span class="sxs-lookup"><span data-stu-id="01abd-108">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="01abd-109">Veraltete Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>-Methode) lesen und erkennen den Wert in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="01abd-109">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01abd-110">Für .NET Framework Version 2.0 und höher ist IPv6 standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="01abd-110">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="01abd-111">Für .NET Framework Version 1.1 und früher ist IPv6 standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="01abd-111">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01abd-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01abd-112">Example</span></span>  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01abd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01abd-113">See Also</span></span>  
 [<span data-ttu-id="01abd-114">IPv6-Adressierung</span><span class="sxs-lookup"><span data-stu-id="01abd-114">IPv6 Addressing</span></span>](../../../docs/framework/network-programming/ipv6-addressing.md)  
 [<span data-ttu-id="01abd-115">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="01abd-115">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="01abd-116">\<IPv6>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="01abd-116">\<ipv6> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
