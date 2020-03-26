---
title: Vereinfachte Konfiguration
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 4e316290c045b75896c61e36c1646440c18678e2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249629"
---
# <a name="simplified-configuration"></a>Vereinfachte Konfiguration
Das Konfigurieren von Windows Communication Foundation (WCF)-Diensten kann eine komplexe Aufgabe sein. Es gibt viele verschiedene Optionen, und es ist nicht immer einfach zu bestimmen, welche Einstellungen erforderlich sind. Konfigurationsdateien erhöhen zwar die Flexibilität von WCF-Diensten, sind aber auch die Quelle für viele schwer zu findende Probleme. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] behandelt diese Probleme und gibt Benutzern die Möglichkeit, den Umfang und die Komplexität der Dienstkonfiguration zu reduzieren.  
  
## <a name="simplified-configuration"></a>Vereinfachte Konfiguration  
 In WCF-Dienstkonfigurationsdateien `system.serviceModel` enthält der Abschnitt `service` <> eine <>-Element für jeden gehosteten Dienst. Das `service` <>-Element enthält `endpoint` eine Auflistung von <> Elementen, die die Endpunkte angeben, die für jeden Dienst verfügbar gemacht werden, und optional eine Reihe von Dienstverhalten. Die `endpoint` <> Elemente die Adresse, Bindung und den Vom Endpunkt verfügbar gemachten Vertrag sowie optional das Bindungskonfigurations- und Endpunktverhalten angeben. Der `system.serviceModel` Abschnitt <> `behaviors` enthält auch ein <>-Element, mit dem Sie Dienst- oder Endpunktverhalten angeben können. Das folgende Beispiel `system.serviceModel` zeigt den <> Abschnitt einer Konfigurationsdatei.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]erleichtert die Konfiguration eines WCF-Dienstes, `service` indem die Anforderung für das <>-Elements entfernt wird. Wenn Sie keinen <`service`> Abschnitt hinzufügen oder Endpunkte in einem <`service`> Abschnitt hinzufügen und Ihr Dienst keine Endpunkte programmgesteuert definiert, wird ihrem Dienst automatisch ein Satz von Standardendpunkten hinzugefügt, einer für jede Dienstbasisadresse und für jeden von Ihrem Dienst implementierten Vertrag. An jedem dieser Endpunkte entspricht die Endpunktadresse der Basisadresse, die Bindung wird anhand des Basisadressenschemas bestimmt, und der Vertrag ist der Vertrag, der vom Dienst implementiert wird. Wenn es nicht erforderlich ist, Endpunkte oder Dienstverhalten anzugeben oder Änderungen an den Bindungseinstellungen vorzunehmen, müssen Sie keine Dienstkonfigurationsdatei angeben. Wenn ein Dienst zwei Verträge implementiert und der Host sowohl HTTP- als auch TCP-Transporte zulässt, erstellt der Diensthost vier Standardendpunkte, einen für jeden Vertrag mit den einzelnen Transporten. Um Standardendpunkte zu erstellen, muss der Diensthost wissen, welche Bindungen verwendet werden können. Diese Einstellungen werden in `protocolMappings` einem <`system.serviceModel`> Abschnitt im Abschnitt <> angegeben. Der `protocolMappings` Abschnitt <> enthält eine Liste der Transportprotokollschemata, die Bindungstypen zugeordnet sind. Der Diensthost verwendet die übergebene Basisadresse, um die zu verwendende Bindung zu ermitteln. Im folgenden Beispiel `protocolMappings` wird das <>-Element verwendet.  
  
> [!WARNING]
> Das Ändern von Standardkonfigurationselementen, z. B. Bindungen oder Verhalten, wirkt sich möglicherweise auf Dienste aus, die auf niedrigeren Ebenen der Konfigurationshierarchie definiert sind, da sie eventuell diese Standardbindungen bzw. dieses Standardverhalten verwenden. Daher muss jede Person, die Standardbindungen und -verhalten ändert, berücksichtigen, dass sich diese Änderungen auf andere Dienste in der Hierarchie auswirken können.  
  
> [!NOTE]
> Unter Internetinformationsdienste (IIS) oder dem Windows-Prozessaktivierungsdienst (WAS) gehostete Dienste verwenden das virtuelle Verzeichnis als Basisadresse.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 Im vorherigen Beispiel verwendet ein Endpunkt mit einer Basisadresse, die mit dem Schema "http" beginnt, das <xref:System.ServiceModel.BasicHttpBinding>-Objekt. Ein Endpunkt mit einer Basisadresse, die mit dem Schema "net.tcp" beginnt, verwendet das <xref:System.ServiceModel.NetTcpBinding>-Objekt. Sie können Einstellungen in einer lokalen App.config- oder Web.config-Datei überschreiben.  
  
 Jedes Element im `protocolMappings` <> Abschnitt muss ein Schema und eine Bindung angeben. Optional kann ein `bindingConfiguration` Attribut angegeben werden, das eine `bindings` Bindungskonfiguration im <> Abschnitt der Konfigurationsdatei angibt. Wenn keine `bindingConfiguration` angegeben wird, wird die anonyme Bindungskonfiguration des entsprechenden Bindungstyps verwendet.  
  
 Das Dienstverhalten wird für die Standardendpunkte `behavior` mithilfe anonymer `serviceBehaviors` <> Abschnitte in <> Abschnitten konfiguriert. Alle unbenannten <`behavior` `serviceBehaviors`> Elemente innerhalb <> werden zum Konfigurieren des Dienstverhaltens verwendet. Die folgende Konfigurationsdatei ermöglicht z. B. die Veröffentlichung von Dienstmetadaten für alle Dienste innerhalb des Hosts.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 Das Endpunktverhalten wird mithilfe anonymer <`behavior`> `serviceBehaviors` Abschnitte in <> Abschnitten konfiguriert.  
  
 Das folgende Beispiel zeigt eine Konfigurationsdatei, die der Datei am Anfang dieses Themas ähnelt, in der das vereinfachte Konfigurationsmodell verwendet wird.  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> Diese Funktion ist nur für die WCF-Dienstkonfiguration, nicht für die Clientkonfiguration relevant. WCF-Clientkonfigurationen werden meistens von einem Tool, z. B. svcutil.exe, oder durch Hinzufügen eines Dienstverweises aus Visual Studio generiert. Wenn Sie einen WCF-Client manuell konfigurieren, \<müssen Sie der Konfiguration ein Client->-Element hinzufügen und alle Endpunkte angeben, die Sie aufrufen möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)
- [Konfigurieren von Bindungen für Dienste](configuring-bindings-for-wcf-services.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](./feature-details/configuring-system-provided-bindings.md)
- [Konfigurieren von Diensten](configuring-services.md)
- [Konfigurieren von WCF-Diensten](configuring-services.md)
- [Konfigurieren von WCF-Diensten in Code](configuring-wcf-services-in-code.md)
