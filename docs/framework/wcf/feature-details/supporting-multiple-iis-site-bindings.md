---
title: Unterstützen mehrerer IIS-Sitebindungen
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 2c42ba7cf3713e5d165d10ce7049df8200d612fb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517873"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Unterstützen mehrerer IIS-Sitebindungen
Wenn ein Windows Communication Foundation (WCF)-Dienst unter IIS 7.0 (Internetinformationsdienste) gehostet wird, empfiehlt es sich um mehrere Basisadressen bereitstellen, die das gleiche Protokoll auf derselben Website zu verwenden. Auf diese Weise kann ein Dienst auf unterschiedliche URIs reagieren. Dies ist nützlich, wenn zum Hosten eines Diensts, die überwacht werden sollen http://www.contoso.com und http://contoso.com. Es ist auch hilfreich, einen Dienst zu erstellen, der über eine Basisadresse für interne Benutzer und eine separate Basisadresse für externe Benutzer verfügt. Zum Beispiel: http://internal.contoso.com und http://www.contoso.com.  
  
> [!NOTE]
>  Diese Funktionalität ist nur bei Verwendung des HTTP-Protokolls verfügbar.  
  
## <a name="multiple-base-addresses"></a>Mehrere Basisadressen  
 Dieses Feature steht nur für WCF-Dienste, die unter IIS gehostet werden. Diese Funktion ist standardmäßig nicht aktiviert. Zur Aktivierung müssen Sie Hinzufügen der `multipleSiteBindingsEnabled` -Attribut auf die <`serviceHostingEnvironment`>-Element in der Web.config Datei, und legen Sie ihn auf `true`, wie im folgenden Beispiel gezeigt.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Wenn Sie einen WCF-Dienst unter IIS hosten, erstellt IIS eine Basisadresse für Sie basierend auf dem URI auf das virtuelle Verzeichnis, das die Anwendung enthält. Sie können zusätzliche Basisadressen hinzufügen, die das gleiche Protokoll verwenden. Verwenden Sie dazu den Internetinformationsdienste-Manager, um der Website eine oder mehrere Bindungen hinzuzufügen. Geben Sie für jede Bindung ein Protokoll (HTTP oder HTTPS), eine IP-Adresse, einen Port und einen Hostnamen an. Weitere Informationen zur Verwendung von Internetinformationsdienste-Manager finden Sie unter [IIS-Manager (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164057). Weitere Informationen zum Hinzufügen von Bindungen zu einer Website finden Sie unter [Erstellen einer Website (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Angeben mehrerer Basisadressen für die gleiche Website wirkt sich auf den Inhalt der WCF-Hilfeseite, Importschema und die vom Dienst generierten WSDL/MEX-Informationen aus. Die WCF-Hilfeseite zeigt an, die Befehlszeile verwenden, um einen WCF-Client zu generieren, der mit dem Dienst kommunizieren können. Diese Befehlszeile enthält nur die erste Adresse, die in der IIS-Bindung für die Website angegeben ist. Genauso wird beim Importieren des Schemas nur die erste Basisadresse verwendet, die in der IIS-Bindung angegeben ist. WSDL- und MEX-Daten enthalten alle Basisadressen, die in den IIS-Bindungen angegeben sind.  
  
> [!WARNING]
>  Wenn ein Dienst über zwei Basisadressen verfügt, eine für interne Benutzer und eine für externe Benutzer, bedeutet dies, dass beide Basisadressen in den vom Dienst generierten WSDL/MEX-Informationen angegeben wurden.
