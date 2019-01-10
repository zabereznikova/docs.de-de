---
title: '&lt;system.serviceModel&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: c2f4a0787f6027d7f57891d4e219758c4a7054ff
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145847"
---
# <a name="ltsystemservicemodelgt"></a>&lt;system.serviceModel&gt;
Dieser Konfigurationsabschnitt enthält alle Elemente der Windows Communication Foundation (WCF)-ServiceModel-Konfiguration.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|In diesem Abschnitt werden zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors` definiert.  Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente. Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen. Jeder Eintrag wird durch seinen eindeutigen `name` identifiziert. Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.|  
|[\<Client >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Dieser Abschnitt enthält eine Liste mit Endpunkten, die ein Client für die Verbindungsherstellung mit einem Dienst verwendet.|  
|[\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|Dieser Abschnitt definiert für WCF und COM-Interop aktivierte COM-Verträge.|  
|[\<CommonBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|Dieser Abschnitt kann nur in der Datei machine.config definiert werden. Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert verhaltenselemente für alle WCF-Endpunkten und-Dienste auf dem Computer bzw.  Wenn ein Verhalten in beiden definiert ist `<commonBehaviors>` und `<behaviors>` Abschnitten, die das Verhalten in der \<Behaviors >-Abschnitt Priorität eingeräumt.|  
|[\<Diagnose >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Dieser Abschnitt enthält Einstellungen für die Diagnosefunktionen von WCF. Der Benutzer kann Ablaufverfolgung, Leistungsindikatoren und den WMI-Anbieter aktivieren/deaktivieren und benutzerdefinierte Meldungsfilter hinzufügen.|  
|[\<Erweiterungen >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|Dieser Abschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte von Erweiterungen erstellen kann.|  
|[\<ProtocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Dieser Abschnitt definiert einen Satz von standardprotokollzuordnungen zwischen transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen.|  
|[\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|In diesem Abschnitt definiert einen Satz von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt.|  
|[\<ServiceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Dieser Abschnitt definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird. Wenn dieser Abschnitt leer ist, wird der Standardtyp verwendet.|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Der Abschnitt enthält eine Auflistung von Diensten. Für jeden in der Assembly definierten Dienst enthält dieses Element ein `service`-Element mit den Einstellungen für den Dienst.|  
|[\<StandardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Dieser Abschnitt definiert eine Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt. Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt. Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert. Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.|
|[\<tracking>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|Dieser Abschnitt definiert die überwachungseinstellungen für einen Workflowdienst.|

### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\<configuration>|Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 WCF fügt den Konfigurationsabschnitten anderer Produkte keine Elemente hinzu.  
  
 WCF-Dienste werden definiert, der `services` Abschnitt der Konfigurationsdatei. Eine Assembly kann eine beliebige Anzahl von Diensten enthalten. Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt. Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.  
  
 Es wird lediglich das `name`-Attribut eines Diensts benötigt.  Standardmäßig beschreibt ein Dienstname den zugrunde liegenden CLR-Typ, der für die Implementierung eines Diensts verwendet wird. Sie können jedoch die ConfigurationName-Eigenschaft eines <xref:System.ServiceModel.ServiceContractAttribute> ändern, um die CLR-Typanforderung zu überschreiben.  
  
 Das `behaviorConfiguration`-Attribut ist optional. Es identifiziert das von einem Dienst verwendete Dienstverhalten. Das von diesem Attribut angegebene Verhalten muss mit einem Dienstverhalten im Gültigkeitsbereich der gleichen Konfigurationsdatei (das heißt derselben Datei oder einer übergeordneten Datei) verknüpft sein.  
  
 Jeder Dienst macht einen oder mehrere in einem `endpoint`-Element definierte Endpunkte verfügbar. Jeder Endpunkt hat eine eigene Adresse und eine eigene Bindung. Alle Bindungen innerhalb der Konfigurationsdatei müssen im Gültigkeitsbereich der Datei definiert sein.  
  
 Bindungen sind durch die Kombination aus `name`-Attribut und `bindingConfiguration`-Attribut mit Endpunkten verknüpft. Das `binding`-Attribut definiert, in welchem Abschnitt die Bindung definiert ist. Das `bindingConfiguration`-Attribut legt fest, welche konfigurierte Bindung innerhalb des Bindungsabschnitts verwendet wird. Ein Bindungsabschnitt kann verschiedene konfigurierte Bindungen definieren.  
  
## <a name="example"></a>Beispiel  
 Hier sehen Sie ein Beispiel einer WCF-Konfigurationsdatei.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
