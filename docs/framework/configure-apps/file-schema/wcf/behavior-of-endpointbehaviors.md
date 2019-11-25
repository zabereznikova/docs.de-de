---
title: <behavior> von <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140809"
---
# <a name="behavior-of-endpointbehaviors"></a>\<Verhalten > von \<endpointBehavior >
Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Endpunkts. Jedes Verhalten wird durch seinen `name` indiziert. Endpunkte können über diesen Namen mit den Verhalten verknüpft sein. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhalten**](behaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpointverhaltensweisen**](endpointbehaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Verhalten >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Clientanmelde Informationen >](clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
|[\<callbackdebug->](callbackdebug.md)|Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.|  
|[\<callbacktimeouts >](callbacktimeouts.md)|Gibt das Timeout für den Clientrückruf an.|  
|[\<clientVia >](clientvia.md)|Gibt die Route an, die eine Nachricht nehmen sollte.|  
|[\<DataContractSerializer >](datacontractserializer.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<dispatchersynchronisierung >](dispatchersynchronization.md)|Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.|  
|[\<enableWebScript >](enablewebscript.md)|Aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann. Das Verhalten sollte nur in Verbindung mit der \<WebHttpBinding > Standard Bindung oder dem \<webMessageEncoding-> Binding-Element verwendet werden.|  
|[\<endpointdiscovery >](endpointdiscovery.md)|Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.|  
|[\<soapprocessing->](soapprocessing.md)|Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.|  
|[\<synchronousreceive >](synchronousreceive-element.md)|Gibt das Laufzeitverhalten für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung an. Es enthält keine Attribute oder untergeordnete Elemente.|  
|[\<von transactedbatching >](transactedbatching.md)|Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.|  
|[\<webHttp->](webhttp.md)|Gibt WebHttpBehavior anhand der Konfiguration in einem Endpunkt an. Wenn dieses Verhalten in Verbindung mit der \<WebHttpBinding > Standard Bindung verwendet wird, wird das webprogrammier Modell für einen WCF-Dienst aktiviert.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<endpointverhaltens >](endpointbehaviors.md)|Eine Auflistung von Endpunktverhaltenselementen.|
