---
title: "Lastenausgleich | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Lastenausgleich [WCF]"
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Lastenausgleich
Eine Möglichkeit, die Kapazität von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen zu erhöhen, besteht darin, sie dezentral zu skalieren und in einer Serverfarm mit Lastenausgleich bereitzustellen.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendungen können mit Standardverfahren zum Lastenausgleich entsprechend ausgeglichen werden. Dazu gehören Softwarelastenausgleichsmodule wie Windows Network Load Balancing sowie hardwarebasierte Anwendungen zum Lastenausgleich.  
  
 In den folgenden Abschnitten werden Überlegungen für den Lastenausgleich von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendungen erläutert, der mit verschiedenen vom System bereitgestellten Bindungen erzielt wird.  
  
## Lastenausgleich mit der Basic\-HTTP\-Bindung  
 Aus der Sicht des Lastenausgleichs unterscheiden sich [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendungen, die mithilfe von <xref:System.ServiceModel.BasicHttpBinding> kommunizieren, nicht von anderen gängigen Arten des HTTP\-Netzwerkdatenverkehrs \(statischem HTML\-Inhalt, ASP.NET\-Seiten oder ASMX\-Webdiensten\).[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Kanäle, die diese Bindung verwenden, weisen grundsätzlich keinen Zustand auf und beenden ihre Verbindungen, wenn der Kanal geschlossen wird.Daher funktioniert die <xref:System.ServiceModel.BasicHttpBinding> gut mit vorhandenen HTTP\-Lastenausgleichstechniken.  
  
 Standardmäßig sendet die <xref:System.ServiceModel.BasicHttpBinding> einen HTTP\-Verbindungsheader in Nachrichten mit einem `Keep-Alive`\-Wert, der Clients ermöglicht, permanente Verbindungen zu den Diensten herzustellen, die sie unterstützen.Diese Konfiguration bietet einen höheren Durchsatz, da zuvor hergestellte Verbindungen erneut verwendet werden können, um nachfolgende Nachrichten an denselben Server zu senden.Die Wiederverwendung der Verbindung kann jedoch dazu führen, dass Clients eng mit einem bestimmten Server innerhalb der Serverfarm mit Lastenausgleich verbunden werden, was die Effektivität des Roundrobin\-Lastenausgleichs reduziert.Wenn dieses Verhalten unerwünscht ist, kann HTTP `Keep-Alive` auf dem Server deaktiviert werden, indem die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A>\-Eigenschaft mit einer <xref:System.ServiceModel.Channels.CustomBinding> oder einer benutzerdefinierten <xref:System.ServiceModel.Channels.Binding> verwendet wird.Im folgenden Beispiel wird gezeigt, wie dieser Vorgang unter Verwendung der Konfiguration ausgeführt wird.  
  
```  
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
      <add scheme=”http” binding=”customBinding” />  
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
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## Lastenausgleich mit der WSHttp\-Bindung und der WSDualHttp\-Bindung  
 Sowohl die <xref:System.ServiceModel.WSHttpBinding> als auch die <xref:System.ServiceModel.WSDualHttpBinding> können mit HTTP\-Lastenausgleichstechniken ausgeglichen werden, vorausgesetzt, an der Standardbindungskonfiguration werden einige Änderungen vorgenommen.  
  
-   Sicherheitskontexterstellung deaktivieren: Dies kann durch Festlegen der <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>\-Eigenschaft der <xref:System.ServiceModel.WSHttpBinding> auf `false` erreicht werden.Wenn Sicherheitssitzungen erforderlich sind, ist es auch möglich, zustandsbehaftete Sicherheitssitzungen zu verwenden, wie im Thema [Sichere Sitzungen](../../../docs/framework/wcf/feature-details/secure-sessions.md) beschrieben.Zustandsbehaftete Sicherheitssitzungen ermöglichen dem Dienst, zustandsfrei zu bleiben, da der gesamte Zustand für die Sicherheitssitzung mit jeder Anforderung als Teil des Schutzsicherheitstokens übertragen wird.Zum Aktivieren einer zustandsbehafteten Sicherheitssitzung muss eine <xref:System.ServiceModel.Channels.CustomBinding> oder eine benutzerdefinierte <xref:System.ServiceModel.Channels.Binding> verwendet werden, da die erforderlichen Konfigurationseinstellungen nicht für die vom System bereitgestellte <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.WSDualHttpBinding> verfügbar gemacht werden.  
  
-   Verwenden Sie keine zuverlässigen Sitzungen.Diese Funktion ist standardmäßig deaktiviert.  
  
## Lastenausgleich der Net.TCP\-Bindung  
 Die <xref:System.ServiceModel.NetTcpBinding> kann mit Lastenausgleichstechniken der IP\-Ebene ausgeglichen werden.Die <xref:System.ServiceModel.NetTcpBinding> legt jedoch TCP\-Verbindungen standardmäßig zusammen, um die Verbindungswartezeit zu reduzieren.Dies ist eine Optimierung, die den grundlegenden Mechanismus des Lastenausgleichs behindert.Der primäre Konfigurationswert zur Optimierung der <xref:System.ServiceModel.NetTcpBinding> ist der Leasetimeout, der zu den Verbindungspooleinstellungen gehört.Verbindungspooling bewirkt, dass Clientverbindungen bestimmten Servern innerhalb der Farm zugeordnet werden.Mit steigender Lebensdauer dieser Verbindung \(ein Faktor, der von der Leasetimeout\-Einstellung gesteuert wird\) wird die Lastenverteilung über die verschiedenen Server auf der Farm zunehmend unausgeglichen.Demzufolge steigt die durchschnittliche Aufrufzeit.Erwägen Sie daher bei der Verwendung der <xref:System.ServiceModel.NetTcpBinding> in Lastenausgleichsszenarien, den von der Bindung verwendeten Leasetimeout\-Standardwert zu reduzieren.Ein 30 Sekunden dauernder Leasetimeout ist ein angemessener Ausgangspunkt für Lastenausgleichsszenarien. Der optimale Wert richtet sich jedoch nach der jeweiligen Anwendung.Weitere Informationen über den Kanal\-Leasetimeout und andere Transportkontingente finden Sie unter [Transportkontingente](../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 Erwägen Sie, für die optimale Leistung in Lastenausgleichsszenarien <xref:System.ServiceModel.NetTcpSecurity> \( <xref:System.ServiceModel.SecurityMode> oder <xref:System.ServiceModel.SecurityMode>\) zu verwenden.  
  
## Siehe auch  
 [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)