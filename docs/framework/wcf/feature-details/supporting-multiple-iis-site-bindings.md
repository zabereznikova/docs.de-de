---
title: Unterstützen mehrerer IIS-Sitebindungen
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 9b92243bb7aaea5c8ecf708ce863e6979bc9f17c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497619"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Unterstützen mehrerer IIS-Sitebindungen
Wenn ein Windows Communication Foundation (WCF)-Dienst unter Internetinformationsdienste (IIS) 7.0 gehostet wird, möchten möglicherweise mehrere Basisadressen bereitstellen, die auf derselben Website das gleiche Protokoll verwenden. Auf diese Weise kann ein Dienst auf unterschiedliche URIs reagieren. Dies ist hilfreich, wenn zum Hosten eines Diensts, die überwacht werden sollen http://www.contoso.com und http://contoso.com. Es ist auch hilfreich, einen Dienst zu erstellen, der über eine Basisadresse für interne Benutzer und eine separate Basisadresse für externe Benutzer verfügt. Zum Beispiel: http://internal.contoso.com und http://www.contoso.com.  
  
> [!NOTE]
>  Diese Funktionalität ist nur bei Verwendung des HTTP-Protokolls verfügbar.  
  
## <a name="multiple-base-addresses"></a>Mehrere Basisadressen  
 Diese Funktion ist nur verfügbar für WCF-Dienste, die unter IIS gehostet werden. Diese Funktion ist standardmäßig nicht aktiviert. Aktivieren Sie hinzufügen müssen der `multipleSiteBindingsEnabled` -Attribut auf der <`serviceHostingEnvironment`>-Element in der Datei "Web.config"-Datei ein, und legen Sie sie auf `true`, wie im folgenden Beispiel gezeigt.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Beim Hosten eines WCF-Diensts unter IIS erstellt IIS eine Basisadresse für basierend auf den URI in das virtuelle Verzeichnis, das die Anwendung enthält. Sie können zusätzliche Basisadressen hinzufügen, die das gleiche Protokoll verwenden. Verwenden Sie dazu den Internetinformationsdienste-Manager, um der Website eine oder mehrere Bindungen hinzuzufügen. Geben Sie für jede Bindung ein Protokoll (HTTP oder HTTPS), eine IP-Adresse, einen Port und einen Hostnamen an. Weitere Informationen zur Verwendung von Internetinformationsdienste-Manager finden Sie unter [IIS-Manager (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057). Weitere Informationen zum Hinzufügen von Bindungen auf einer Website finden Sie unter [Erstellen einer Website (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Angeben mehrerer Basisadressen für die gleiche Website wirkt sich auf den Inhalt der WCF-Hilfeseite Importschema und die vom Dienst generierten WSDL/MEX-Informationen aus. Die WCF-Hilfeseite zeigt die Befehlszeile verwenden, um einen WCF-Client zu generieren, der mit dem Dienst kommunizieren können. Diese Befehlszeile enthält nur die erste Adresse, die in der IIS-Bindung für die Website angegeben ist. Genauso wird beim Importieren des Schemas nur die erste Basisadresse verwendet, die in der IIS-Bindung angegeben ist. WSDL- und MEX-Daten enthalten alle Basisadressen, die in den IIS-Bindungen angegeben sind.  
  
> [!WARNING]
>  Wenn ein Dienst über zwei Basisadressen verfügt, eine für interne Benutzer und eine für externe Benutzer, bedeutet dies, dass beide Basisadressen in den vom Dienst generierten WSDL/MEX-Informationen angegeben wurden.
