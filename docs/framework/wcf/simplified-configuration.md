---
title: Vereinfachte Konfiguration
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 13cf8bd46ef3aabb011cb2ddd207963235468662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967894"
---
# <a name="simplified-configuration"></a>Vereinfachte Konfiguration
Konfigurieren von Windows Communication Foundation (WCF)-Diensten kann eine komplexe Aufgabe sein. Es gibt viele verschiedene Optionen, und es ist nicht immer einfach zu bestimmen, welche Einstellungen erforderlich sind. Konfigurationsdateien erhöhen, zwar die Flexibilität von WCF-Diensten sind sie auch die Quelle für viele schwierig, Probleme zu finden. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] behandelt diese Probleme und gibt Benutzern die Möglichkeit, den Umfang und die Komplexität der Dienstkonfiguration zu reduzieren.  
  
## <a name="simplified-configuration"></a>Vereinfachte Konfiguration  
 In WCF-Dienst-Konfigurationsdateien die <`system.serviceModel`> Abschnitt enthält eine <`service`>-Element für jeden gehosteten Dienst. Die <`service`>-Element enthält eine Auflistung von <`endpoint`>-Elemente, die die Endpunkte für die einzelnen Dienste und optional ein Satz von Dienstverhalten angeben. Die <`endpoint`>-Elemente geben die Adresse, Bindung und Vertrag verfügbar gemacht, von dem Endpunkt und optional Bindungskonfiguration und die Endpunktverhalten. Die <`system.serviceModel`> Abschnitt enthält auch eine <`behaviors`>-Element, das Sie Dienst- oder Endpunktverhaltensweisen angeben kann. Das folgende Beispiel zeigt die <`system.serviceModel`>-Abschnitt einer Konfigurationsdatei.  
  
```  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] vereinfacht das Konfigurieren eines WCF-Diensts einfacher durch die Anforderung für die <`service`> Element. Wenn Sie keine hinzufügen eine <`service`>-Abschnitt oder keine Endpunkte in hinzufügen eine <`service`> Abschnitt und der Dienst wird programmgesteuert definieren Sie keine Endpunkte, und klicken Sie dann ein Satz von Standardendpunkten werden automatisch für jeden Dienst hinzugefügt Service Basisadresse und für jeden vom Dienst implementierten Vertrag. An jedem dieser Endpunkte entspricht die Endpunktadresse der Basisadresse, die Bindung wird anhand des Basisadressenschemas bestimmt, und der Vertrag ist der Vertrag, der vom Dienst implementiert wird. Wenn es nicht erforderlich ist, Endpunkte oder Dienstverhalten anzugeben oder Änderungen an den Bindungseinstellungen vorzunehmen, müssen Sie keine Dienstkonfigurationsdatei angeben. Wenn ein Dienst zwei Verträge implementiert und der Host sowohl HTTP- als auch TCP-Transporte zulässt, erstellt der Diensthost vier Standardendpunkte, einen für jeden Vertrag mit den einzelnen Transporten. Um Standardendpunkte zu erstellen, muss der Diensthost wissen, welche Bindungen verwendet werden können. Diese Einstellungen werden angegeben, einem <`protocolMappings`>-Abschnitt innerhalb der <`system.serviceModel`> Abschnitt. Die <`protocolMappings`> Abschnitt enthält eine Liste von transportprotokollschemas, die Bindungstypen zugeordnet. Der Diensthost verwendet die übergebene Basisadresse, um die zu verwendende Bindung zu ermitteln. Im folgenden Beispiel wird die <`protocolMappings`> Element.  
  
> [!WARNING]
>  Das Ändern von Standardkonfigurationselementen, z. B. Bindungen oder Verhalten, wirkt sich möglicherweise auf Dienste aus, die auf niedrigeren Ebenen der Konfigurationshierarchie definiert sind, da sie eventuell diese Standardbindungen bzw. dieses Standardverhalten verwenden. Daher muss jede Person, die Standardbindungen und -verhalten ändert, berücksichtigen, dass sich diese Änderungen auf andere Dienste in der Hierarchie auswirken können.  
  
> [!NOTE]
>  Unter Internetinformationsdienste (IIS) oder dem Windows-Prozessaktivierungsdienst (WAS) gehostete Dienste verwenden das virtuelle Verzeichnis als Basisadresse.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 Im vorherigen Beispiel verwendet ein Endpunkt mit einer Basisadresse, die mit dem Schema "http" beginnt, das <xref:System.ServiceModel.BasicHttpBinding>-Objekt. Ein Endpunkt mit einer Basisadresse, die mit dem Schema "net.tcp" beginnt, verwendet das <xref:System.ServiceModel.NetTcpBinding>-Objekt. Sie können Einstellungen in einer lokalen App.config- oder Web.config-Datei überschreiben.  
  
 Jedes Element innerhalb der <`protocolMappings`> Abschnitt muss ein Schema und eine Bindung angeben. Optional können sie angeben eine `bindingConfiguration` -Attribut, das eine Bindungskonfiguration im gibt an, die <`bindings`>-Abschnitt der Konfigurationsdatei. Wenn keine `bindingConfiguration` angegeben wird, wird die anonyme Bindungskonfiguration des entsprechenden Bindungstyps verwendet.  
  
 Dienstverhaltensweisen werden für die Standardendpunkte konfiguriert, indem anonyme <`behavior`>-Abschnitte innerhalb <`serviceBehaviors`> Abschnitte. Alle unbenannten <`behavior`>-Elemente innerhalb von <`serviceBehaviors`> werden verwendet, um Dienstverhaltensweisen zu konfigurieren. Die folgende Konfigurationsdatei ermöglicht z. B. die Veröffentlichung von Dienstmetadaten für alle Dienste innerhalb des Hosts.  
  
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
  
 Endpunktverhaltensweisen werden konfiguriert, indem anonyme <`behavior`>-Abschnitte innerhalb <`serviceBehaviors`> Abschnitte.  
  
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
>  Diese Funktion ist nur für die WCF-Dienstkonfiguration, nicht für die Clientkonfiguration relevant. WCF-Clientkonfigurationen werden meistens von einem Tool, z. B. svcutil.exe, oder durch Hinzufügen eines Dienstverweises aus Visual Studio generiert. Wenn Sie einen WCF-Client manuell konfigurieren müssen Sie Hinzufügen einer \<Client >-Element an der Konfiguration, und geben Sie alle Endpunkte, die Sie aufrufen möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Konfigurieren von Bindungen für Dienste](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Konfigurieren von Diensten](../../../docs/framework/wcf/configuring-services.md)
- [Konfigurieren von WCF-Diensten](configuring-services.md)
- [Konfigurieren von WCF-Diensten in Code](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
