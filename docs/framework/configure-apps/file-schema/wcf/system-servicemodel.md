---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399442"
---
# \<system.serviceModel>
Dieser Konfigurations Abschnitt enthält alle Service Model-Konfigurationselemente Windows Communication Foundation (WCF).  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
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
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|In diesem Abschnitt werden zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors` definiert.  Jede Auflistung definiert von Endpunkten und Diensten verwendete Verhaltenselemente. Jedes Verhaltenselement wird durch seinen eindeutigen `name` identifiziert.|  
|[\<bindings>](bindings.md)|Dieser Abschnitt enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen. Jeder Eintrag wird durch seinen eindeutigen `name` identifiziert. Dienste verwenden Bindungen, indem sie sie mithilfe des `name` verknüpfen.|  
|[\<client>](client.md)|Dieser Abschnitt enthält eine Liste mit Endpunkten, die ein Client für die Verbindungsherstellung mit einem Dienst verwendet.|  
|[\<comContracts>](comcontracts.md)|Dieser Abschnitt definiert für WCF und COM-Interop aktivierte COM-Verträge.|  
|[\<commonBehaviors>](commonbehaviors.md)|Dieser Abschnitt kann nur in der Datei machine.config definiert werden. Er definiert zwei untergeordnete Auflistungen mit den Namen `endpointBehaviors` und `serviceBehaviors`.  Jede Auflistung definiert Verhaltenselemente, die von allen WCF-Endpunkten und-Diensten auf dem Computer verwendet werden.  Wenn ein Verhalten im `<commonBehaviors>`-Abschnitt und im `<behaviors>`-Abschnitt definiert ist, wird dem Verhalten im \<behaviors>-Abschnitt Priorität eingeräumt.|  
|[\<diagnostics>](diagnostics.md)|Dieser Abschnitt enthält Einstellungen für die Diagnosefunktionen von WCF. Der Benutzer kann Ablaufverfolgung, Leistungsindikatoren und den WMI-Anbieter aktivieren/deaktivieren und benutzerdefinierte Meldungsfilter hinzufügen.|  
|[\<extensions>](extensions-section.md)|Dieser Abschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte von Erweiterungen erstellen kann.|  
|[\<protocolMapping>](protocolmapping.md)|Dieser Abschnitt definiert einen Satz von Standardprotokollzuordnungen zwischen Transportprotokollschemas (z. B. http, net.tcp, net.pipe usw.) und WCF-Bindungen.|  
|[\<routing>](routing.md)|Dieser Abschnitt definiert einen Satz von Routing filtern, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|Dieser Abschnitt definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird. Wenn dieser Abschnitt leer ist, wird der Standardtyp verwendet.|  
|[\<services>](services.md)|Der Abschnitt enthält eine Auflistung von Diensten. Für jeden in der Assembly definierten Dienst enthält dieses Element ein `service`-Element mit den Einstellungen für den Dienst.|  
|[\<standardEndpoints>](standardendpoints.md)|Dieser Abschnitt definiert eine Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt. Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt. Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert. Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.|
|[\<tracking>](tracking-of-wcf.md)|In diesem Abschnitt werden die Überwachungs Einstellungen für einen Workflow Dienst definiert.|

### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|\<configuration>|Das Stammelement für alle Konfigurationselemente in einer Konfigurationsdatei.|  
  
## <a name="remarks"></a>Bemerkungen  
 WCF fügt den Konfigurations Abschnitten anderer Produkte keine Elemente hinzu.  
  
 WCF-Dienste werden im- `services` Abschnitt der Konfigurationsdatei definiert. Eine Assembly kann eine beliebige Anzahl von Diensten enthalten. Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt. Dieser Abschnitt und sein Inhalt definieren den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
