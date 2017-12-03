---
title: "Unterstützen mehrerer IIS-Sitebindungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bf2dbccd81b9c2e7b4ec78863d3de0227baedf92
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="supporting-multiple-iis-site-bindings"></a>Unterstützen mehrerer IIS-Sitebindungen
Beim Hosten eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensts unter Internetinformationsdienste (IIS) 7.0 sollten Sie mehrere Basisadressen bereitstellen, die das gleiche Protokoll auf der gleichen Website verwenden. Auf diese Weise kann ein Dienst auf unterschiedliche URIs reagieren. Dies ist nützlich, wenn Sie einen Dienst hosten möchten, der "http://www.contoso.com" und "http://contoso.com" überwacht. Es ist auch hilfreich, einen Dienst zu erstellen, der über eine Basisadresse für interne Benutzer und eine separate Basisadresse für externe Benutzer verfügt. Beispiel: http://internal.contoso.com und http://www.contoso.com.  
  
> [!NOTE]
>  Diese Funktionalität ist nur bei Verwendung des HTTP-Protokolls verfügbar.  
  
## <a name="multiple-base-addresses"></a>Mehrere Basisadressen  
 Diese Funktion ist nur für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste verfügbar, die unter IIS gehostet werden. Diese Funktion ist standardmäßig nicht aktiviert. Aktivieren Sie hinzufügen müssen der `multipleSiteBindingsEnabled` -Attribut auf der <`serviceHostingEnvironment`>-Element in der Datei "Web.config"-Datei ein, und legen Sie sie auf `true`, wie im folgenden Beispiel gezeigt.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Beim Hosten eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts unter IIS erstellt IIS basierend auf dem URI zum virtuellen Verzeichnis, das die Anwendung enthält, eine Basisadresse. Sie können zusätzliche Basisadressen hinzufügen, die das gleiche Protokoll verwenden. Verwenden Sie dazu den Internetinformationsdienste-Manager, um der Website eine oder mehrere Bindungen hinzuzufügen. Geben Sie für jede Bindung ein Protokoll (HTTP oder HTTPS), eine IP-Adresse, einen Port und einen Hostnamen an. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]verwenden Internetinformationsdienste-Manager, finden Sie unter [IIS-Manager (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Bindungen zu einem Standort hinzuzufügen, finden Sie unter [Erstellen einer Website (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Das Angeben mehrerer Basisadressen für die gleiche Website wirkt sich auf den Inhalt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Hilfeseite, das Importschema und die vom Dienst generierten WSDL/MEX-Informationen aus. Die Hilfeseite von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zeigt die Befehlszeile an, die zum Generieren eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients verwendet wird, der mit dem Dienst kommunizieren kann. Diese Befehlszeile enthält nur die erste Adresse, die in der IIS-Bindung für die Website angegeben ist. Genauso wird beim Importieren des Schemas nur die erste Basisadresse verwendet, die in der IIS-Bindung angegeben ist. WSDL- und MEX-Daten enthalten alle Basisadressen, die in den IIS-Bindungen angegeben sind.  
  
> [!WARNING]
>  Wenn ein Dienst über zwei Basisadressen verfügt, eine für interne Benutzer und eine für externe Benutzer, bedeutet dies, dass beide Basisadressen in den vom Dienst generierten WSDL/MEX-Informationen angegeben wurden.
