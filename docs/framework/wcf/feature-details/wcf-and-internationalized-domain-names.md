---
title: WCF und internationale Domänennamen
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 1db62f3e7d073fd1bf9bf9d4d0e17703310f2e69
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988587"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF und internationale Domänennamen
Unterstützung für WCF-Dienste mit internationalisierten Domänennamen (Internationalized Domain Names, IDNs) wurde hinzugefügt. Ein internationalisierter Domänenname ist ein Domänenname, der Nicht-ASCII-Zeichen enthält. Diese Unterstützung umfasst die Fähigkeit zum Hosten eines WCF-Diensts mit einem IDN und zum Kommunizieren eines WCF-Clients mit einem Webdienst, der über einen IDN verfügt.  
  
## <a name="systemuri-and-idn"></a>System.Uri und IDN  
 <xref:System.Uri> verfügt über die beiden Eigenschaften <xref:System.Uri.Host%2A> und <xref:System.Uri.DnsSafeHost%2A>. Diese Eigenschaften enthalten abhängig von den IDN-Konfigurationseinstellungen Unicode- oder Punycode-Werte.  
  
 IDN wird in der Konfigurationsdatei einer Anwendung mit dem folgenden XML-Code aktiviert:  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 Das \<IDN->-Element enthält das aktivierte Attribut, das auf einen der folgenden Werte festgelegt werden kann:  
  
1. Gar  
  
2. AllExceptIntranet  
  
3. Allen  
  
 Wenn die IDN-Einstellung auf "None" festgelegt ist, werden keine Konvertierungen von "URI. Host" oder "URI. DnsSafeHost" durchgeführt. Wenn die IDN-Einstellung auf "All" festgelegt ist, Uri. Der Host bleibt Unicode und der URI. DnsSafeHost wird in Punycode konvertiert. Wenn die IDN-Einstellung auf "AllExceptIntranet", URI festgelegt ist. DnsSafeHost wird für Internetadressen in Punycode konvertiert und bleibt für Intranetadressen Unicode. Diese Einstellung ist für eine ordnungsgemäße DNS-Namensauflösung wichtig. Beachten Sie, dass diese Einstellung für Windows 8 und spätere Versionen nicht konfiguriert werden muss.  
  
> [!WARNING]
> Sie sollten eine Adresse nie mit Punycode hartcodieren. WCF konvertiert sie auf Grundlage der verwendeten Konfigurationseinstellungen.  
  
> [!WARNING]
> Wenn Sie applicationHost.exe.config Unicode-Zeichen hinzufügen, speichern Sie die Datei mit UTF-8-Codierung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Uri?displayProperty=nameWithType>
