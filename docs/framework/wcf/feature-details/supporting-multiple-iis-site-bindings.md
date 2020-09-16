---
title: Unterstützen mehrerer IIS-Sitebindungen
description: Erfahren Sie, wie Sie mehrere Basisadressen bereitstellen, die das gleiche Protokoll auf derselben Website verwenden, wenn Sie einen WCF-Dienst in IIS gehostet haben.
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 6af4d885c7fc3d4dcc12ffb4bf6670f1a9b3d78c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546197"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Unterstützen mehrerer IIS-Sitebindungen
Wenn Sie einen Windows Communication Foundation (WCF)-Dienst unter Internetinformationsdienste (IIS) 7,0 verwenden, möchten Sie möglicherweise mehrere Basisadressen bereitstellen, die das gleiche Protokoll auf derselben Website verwenden. Auf diese Weise kann ein Dienst auf unterschiedliche URIs reagieren. Dies ist hilfreich, wenn Sie einen Dienst hosten möchten, der auf und lauscht `http://www.contoso.com` `http://contoso.com` . Es ist auch hilfreich, einen Dienst zu erstellen, der über eine Basisadresse für interne Benutzer und eine separate Basisadresse für externe Benutzer verfügt. Beispiel: `http://internal.contoso.com` und `http://www.contoso.com`.  
  
> [!NOTE]
> Diese Funktionalität ist nur bei Verwendung des HTTP-Protokolls verfügbar.  
  
## <a name="multiple-base-addresses"></a>Mehrere Basisadressen  
 Diese Funktion ist nur für WCF-Dienste verfügbar, die unter IIS gehostet werden. Diese Funktion ist standardmäßig nicht aktiviert. Um es zu aktivieren, müssen Sie das `multipleSiteBindingsEnabled` -Attribut dem <`serviceHostingEnvironment`>-Element in der Web.config Datei hinzufügen und es auf festlegen `true` , wie im folgenden Beispiel gezeigt.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Wenn ein WCF-Dienst unter IIS gehostet wird, erstellt IIS eine Basisadresse für Sie basierend auf dem URI des virtuellen Verzeichnisses, das die Anwendung enthält. Sie können zusätzliche Basisadressen hinzufügen, die das gleiche Protokoll verwenden. Verwenden Sie dazu den Internetinformationsdienste-Manager, um der Website eine oder mehrere Bindungen hinzuzufügen. Geben Sie für jede Bindung ein Protokoll (HTTP oder HTTPS), eine IP-Adresse, einen Port und einen Hostnamen an. Weitere Informationen zur Verwendung von Internetinformationsdienste Manager finden Sie unter [IIS-Manager (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753842(v=ws.10)). Weitere Informationen zum Hinzufügen von Bindungen zu einer Site finden Sie unter [Erstellen einer Website (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772350(v=ws.10)) .  
  
 Das Angeben mehrerer Basisadressen für denselben Standort wirkt sich auf den Inhalt der WCF-Hilfeseite, das Importieren des Schemas und die vom Dienst generierten WSDL/MEX-Informationen aus. Die WCF-Hilfeseite zeigt die Befehlszeile an, die zum Generieren eines WCF-Clients verwendet werden kann, der mit dem Dienst kommunizieren kann. Diese Befehlszeile enthält nur die erste Adresse, die in der IIS-Bindung für die Website angegeben ist. Genauso wird beim Importieren des Schemas nur die erste Basisadresse verwendet, die in der IIS-Bindung angegeben ist. WSDL- und MEX-Daten enthalten alle Basisadressen, die in den IIS-Bindungen angegeben sind.  
  
> [!WARNING]
> Wenn ein Dienst über zwei Basisadressen verfügt, eine für interne Benutzer und eine für externe Benutzer, bedeutet dies, dass beide Basisadressen in den vom Dienst generierten WSDL/MEX-Informationen angegeben wurden.
