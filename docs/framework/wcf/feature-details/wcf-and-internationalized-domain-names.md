---
title: WCF und internationale Domänennamen
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: 8431f5d47aa32d1c928190abdd3079831ca48618
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44033240"
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
  
 Die \<Idn >-Element enthält das aktivierte Attribut, das auf einen der folgenden Werte festgelegt werden kann:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "Alle"  
  
 Wenn die IDN-Einstellung auf "None" festgelegt ist, werden keine Konvertierungen von Uri.Host oder Uri.DnsSafeHost durchgeführt. Wenn die IDN-Einstellung auf "All"-Uri festgelegt wird. Host bleibt Unicode und Uri. DnsSafeHost wird in Ihre Punycode-Entsprechungen konvertiert. Wenn die IDN-Einstellung auf "AllExceptIntranet", Uri festgelegt ist. DnsSafeHost für Internetadressen in Punycode konvertiert wird, und Unicode für Intranetadressen bleibt. Diese Einstellung ist für eine ordnungsgemäße DNS-Namensauflösung wichtig. Beachten Sie, dass diese Einstellung für Windows 8 und spätere Versionen nicht konfiguriert werden muss.  
  
> [!WARNING]
>  Sie sollten eine Adresse nie mit Punycode hartcodieren. WCF konvertiert sie auf Grundlage der verwendeten Konfigurationseinstellungen.  
  
> [!WARNING]
>  Wenn Sie applicationHost.exe.config Unicode-Zeichen hinzufügen, speichern Sie die Datei mit UTF-8-Codierung.  
  
## <a name="see-also"></a>Siehe auch  
 [System.Uri](https://msdn.microsoft.com/library/system.uri.aspx)
