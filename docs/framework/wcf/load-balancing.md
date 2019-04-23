---
title: Lastenausgleich
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: a43546b9cbb95cd16c1d94372e786acd103ea0bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228632"
---
# <a name="load-balancing"></a>Lastenausgleich
Eine Möglichkeit zum Erhöhen der Kapazität von Windows Communication Foundation (WCF)-Anwendungen besteht darin, skalieren und in einer Serverfarm mit Lastenausgleich. WCF-Anwendungen können mithilfe von Standardverfahren zum, dazu gehören softwarelastenausgleichsmodule wie Windows Network Load Balancing sowie hardwarebasierte Load ausgeglichen werden.  
  
 Den folgenden Abschnitten werden Überlegungen für den Lastenausgleich von WCF-Anwendungen, die mit verschiedenen vom System bereitgestellten Bindungen erstellt wurden.  
  
## <a name="load-balancing-with-the-basic-http-binding"></a>Lastenausgleich mit der Basic-HTTP-Bindung  
 Aus Sicht des Lastenausgleichs, WCF-Anwendungen, die Kommunikation über die <xref:System.ServiceModel.BasicHttpBinding> unterscheiden sich nicht als Netzwerk anderen gängigen Arten des HTTP-Datenverkehr (statische HTML-Inhalt, ASP.NET-Seiten oder ASMX Web Services). WCF-Kanälen, die diese Bindung verwenden, weisen grundsätzlich keinen Zustand, und beenden ihre Verbindungen, wenn der Kanal geschlossen wird. Daher funktioniert die <xref:System.ServiceModel.BasicHttpBinding> gut mit vorhandenen HTTP-Lastenausgleichstechniken.  
  
 Standardmäßig sendet die <xref:System.ServiceModel.BasicHttpBinding> einen HTTP-Verbindungsheader in Nachrichten mit einem `Keep-Alive`-Wert, der Clients ermöglicht, permanente Verbindungen zu den Diensten herzustellen, die sie unterstützen. Diese Konfiguration bietet einen höheren Durchsatz, da zuvor hergestellte Verbindungen erneut verwendet werden können, um nachfolgende Nachrichten an denselben Server zu senden. Die Wiederverwendung der Verbindung kann jedoch dazu führen, dass Clients eng mit einem bestimmten Server innerhalb der Serverfarm mit Lastenausgleich verbunden werden, was die Effektivität des Roundrobin-Lastenausgleichs reduziert. Wenn dieses Verhalten unerwünscht ist, kann HTTP `Keep-Alive` auf dem Server deaktiviert werden, indem die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A>-Eigenschaft mit einer <xref:System.ServiceModel.Channels.CustomBinding> oder einer benutzerdefinierten <xref:System.ServiceModel.Channels.Binding> verwendet wird. Im folgenden Beispiel wird gezeigt, wie dieser Vorgang unter Verwendung der Konfiguration ausgeführt wird.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service   
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"   
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Wenn Sie die in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] eingeführte vereinfachte Konfiguration verwenden, kann das gleiche Verhalten mit der folgenden vereinfachten Konfiguration erreicht werden.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a>Lastenausgleich mit der WSHttp-Bindung und der WSDualHttp-Bindung  
 Sowohl die <xref:System.ServiceModel.WSHttpBinding> als auch die <xref:System.ServiceModel.WSDualHttpBinding> können mit HTTP-Lastenausgleichstechniken ausgeglichen werden, vorausgesetzt, an der Standardbindungskonfiguration werden einige Änderungen vorgenommen.  
  
-   Sicherheitskontexterstellung deaktivieren: Dies kann durch Festlegen der <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft der <xref:System.ServiceModel.WSHttpBinding> auf `false` erreicht werden. Auch wenn sicherheitssitzungen erforderlich sind, es ist möglich, zustandsbehaftete sicherheitssitzungen zu verwenden, siehe die [sichere Sitzungen](../../../docs/framework/wcf/feature-details/secure-sessions.md) Thema. Zustandsbehaftete Sicherheitssitzungen ermöglichen dem Dienst, zustandslos zu bleiben, da der gesamte Zustand für die Sicherheitssitzung mit jeder Anforderung als Teil des Schutzsicherheitstokens übertragen wird. Zum Aktivieren einer zustandsbehafteten Sicherheitssitzung muss eine <xref:System.ServiceModel.Channels.CustomBinding> oder eine benutzerdefinierte <xref:System.ServiceModel.Channels.Binding> verwendet werden, da die erforderlichen Konfigurationseinstellungen nicht für die vom System bereitgestellte <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.WSDualHttpBinding> verfügbar gemacht werden.  
  
-   Verwenden Sie keine zuverlässigen Sitzungen. Diese Funktion ist standardmäßig deaktiviert.  
  
## <a name="load-balancing-the-nettcp-binding"></a>Lastenausgleich der Net.TCP-Bindung  
 Für die <xref:System.ServiceModel.NetTcpBinding> kann mit Lastenausgleichstechniken der IP-Ebene ein Lastausgleich vorgenommen werden. Die <xref:System.ServiceModel.NetTcpBinding> legt jedoch TCP-Verbindungen standardmäßig zusammen, um die Verbindungswartezeit zu reduzieren. Dies ist eine Optimierung, die den grundlegenden Mechanismus des Lastenausgleichs behindert. Der primäre Konfigurationswert zur Optimierung der <xref:System.ServiceModel.NetTcpBinding> ist der Leasetimeout, der zu den Verbindungspooleinstellungen gehört. Verbindungspooling bewirkt, dass Clientverbindungen bestimmten Servern innerhalb der Farm zugeordnet werden. Mit steigender Lebensdauer dieser Verbindung (ein Faktor, der von der Leasetimeout-Einstellung gesteuert wird) wird die Lastenverteilung über die verschiedenen Server auf der Farm zunehmend unausgeglichen. Demzufolge steigt die durchschnittliche Aufrufzeit. Erwägen Sie daher bei der Verwendung der <xref:System.ServiceModel.NetTcpBinding> in Lastenausgleichsszenarien, den von der Bindung verwendeten Leasetimeout-Standardwert zu reduzieren. Ein 30 Sekunden dauernder Leasetimeout ist ein angemessener Ausgangspunkt für Lastenausgleichsszenarien. Der optimale Wert richtet sich jedoch nach der jeweiligen Anwendung. Weitere Informationen über den Kanal-LeaseTimeout und andere transportkontingente finden Sie unter [Transportkontingente](../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 Erwägen Sie, für die optimale Leistung in Lastenausgleichsszenarien <xref:System.ServiceModel.NetTcpSecurity> ( <xref:System.ServiceModel.SecurityMode.Transport> oder <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>) zu verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
