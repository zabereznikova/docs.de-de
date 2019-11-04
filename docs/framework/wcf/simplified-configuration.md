---
title: Vereinfachte Konfiguration
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 3bed6fe961712c976d5e1446ace43e7073036697
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423710"
---
# <a name="simplified-configuration"></a>Vereinfachte Konfiguration
Das Konfigurieren von Windows Communication Foundation (WCF)-Diensten kann eine komplexe Aufgabe sein. Es gibt viele verschiedene Optionen, und es ist nicht immer einfach zu bestimmen, welche Einstellungen erforderlich sind. Konfigurationsdateien erhöhen zwar die Flexibilität von WCF-Diensten, Sie sind jedoch auch die Quelle für viele schwer zu suchende Probleme. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] behandelt diese Probleme und gibt Benutzern die Möglichkeit, den Umfang und die Komplexität der Dienstkonfiguration zu reduzieren.  
  
## <a name="simplified-configuration"></a>Vereinfachte Konfiguration  
 In den WCF-Dienst Konfigurationsdateien enthält der < `system.serviceModel`-> Abschnitt ein < `service`-Element für jeden gehosteten Dienst. Das < `service` >-Element enthält eine Auflistung der < `endpoint` > Elemente, die die für jeden Dienst verfügbar gemachten Endpunkte und optional einen Satz von Dienst Verhaltensweisen angeben. Die < `endpoint` >-Elemente geben die Adresse, die Bindung und den Vertrag an, die vom Endpunkt verfügbar gemacht werden, und optional die Bindungs Konfiguration und das Endpunkt Verhalten. Der > Abschnitt < `system.serviceModel` enthält auch ein < `behaviors`-Element, mit dem Sie Dienst-oder Endpunkt Verhaltensweisen angeben können. Das folgende Beispiel zeigt den < `system.serviceModel`-> Abschnitt einer Konfigurationsdatei.  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
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
  
 mit [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] wird das Konfigurieren eines WCF-Dienstanbieter vereinfacht, indem die Anforderung für das <`service`> Element entfernt wird. Wenn Sie keine <`service`> Abschnitt hinzufügen oder Endpunkte in einem <`service`> Abschnitt hinzufügen und der Dienst keine Endpunkte Programm gesteuert definiert, wird dem Dienst automatisch ein Satz von Standard Endpunkten hinzugefügt, einer für jede Dienst Basis. Adresse und für jeden Vertrag, der von Ihrem Dienst implementiert wird. An jedem dieser Endpunkte entspricht die Endpunktadresse der Basisadresse, die Bindung wird anhand des Basisadressenschemas bestimmt, und der Vertrag ist der Vertrag, der vom Dienst implementiert wird. Wenn es nicht erforderlich ist, Endpunkte oder Dienstverhalten anzugeben oder Änderungen an den Bindungseinstellungen vorzunehmen, müssen Sie keine Dienstkonfigurationsdatei angeben. Wenn ein Dienst zwei Verträge implementiert und der Host sowohl HTTP- als auch TCP-Transporte zulässt, erstellt der Diensthost vier Standardendpunkte, einen für jeden Vertrag mit den einzelnen Transporten. Um Standardendpunkte zu erstellen, muss der Diensthost wissen, welche Bindungen verwendet werden können. Diese Einstellungen werden in einem < `protocolMappings`-> Abschnitt im Abschnitt < `system.serviceModel` > angegeben. Der > Abschnitt < `protocolMappings` enthält eine Liste von Transportprotokoll Schemas, die Bindungs Typen zugeordnet sind. Der Diensthost verwendet die übergebene Basisadresse, um die zu verwendende Bindung zu ermitteln. Im folgenden Beispiel wird das < `protocolMappings` >-Element verwendet.  
  
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
  
 Jedes Element im < `protocolMappings` > Abschnitt muss ein Schema und eine Bindung angeben. Optional kann ein `bindingConfiguration`-Attribut angegeben werden, das eine Bindungs Konfiguration innerhalb des > Abschnitts < `bindings` der Konfigurationsdatei angibt. Wenn keine `bindingConfiguration` angegeben wird, wird die anonyme Bindungskonfiguration des entsprechenden Bindungstyps verwendet.  
  
 Dienst Verhaltensweisen werden für die Standard Endpunkte konfiguriert, indem anonyme < `behavior` > Abschnitte innerhalb < `serviceBehaviors` > Abschnitte verwendet werden. Alle unbenannten < `behavior`-> Elemente in < `serviceBehaviors`-> werden verwendet, um Dienst Verhaltensweisen zu konfigurieren. Die folgende Konfigurationsdatei ermöglicht z. B. die Veröffentlichung von Dienstmetadaten für alle Dienste innerhalb des Hosts.  
  
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
  
 Endpunkt Verhaltensweisen werden mithilfe der anonymen < `behavior` > Abschnitte in < `serviceBehaviors` > Abschnitten konfiguriert.  
  
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
> Diese Funktion ist nur für die WCF-Dienstkonfiguration, nicht für die Clientkonfiguration relevant. WCF-Clientkonfigurationen werden meistens von einem Tool, z. B. svcutil.exe, oder durch Hinzufügen eines Dienstverweises aus Visual Studio generiert. Wenn Sie einen WCF-Client manuell konfigurieren, müssen Sie der Konfiguration ein \<client >-Element hinzufügen und alle Endpunkte angeben, die Sie abrufen möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)
- [Konfigurieren von Bindungen für Dienste](configuring-bindings-for-wcf-services.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](./feature-details/configuring-system-provided-bindings.md)
- [Konfigurieren von Diensten](configuring-services.md)
- [Konfigurieren von WCF-Diensten](configuring-services.md)
- [Konfigurieren von WCF-Diensten in Code](configuring-wcf-services-in-code.md)
