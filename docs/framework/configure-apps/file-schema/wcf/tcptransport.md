---
title: "&lt;tcpTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;tcpTransport&gt;
Definiert einen TCP\-Transport, der von einem Kanal zum Übertragen von Nachrichten für eine benutzerdefinierte Bindung verwendet werden kann.  
  
## Syntax  
  
```  
  
<tcpTransport   
    listenBacklog="Integer"  
        portSharingEnabled="Boolean"  
    teredoEnabled="Boolean"  
    transferMode=”Buffered/Streamed”  
        <connectionPoolSettings  
          groupName=”String”  
        idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|channelInitializationTimeout|Die maximale Zeit in Sekunden, in der sich der Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird.  Dieses Kontingent umfasst die Zeit, die eine TCP\-Verbindung beanspruchen darf, um sich über das .NET Message Framing\-Protokoll zu authentifizieren.  Ein Client muss vorab einige Daten senden, bevor der Server über genügend Informationen zum Ausführen der Authentifizierung verfügt.  Der Standardwert ist 30 Sekunden.|  
|listenBacklog|Die maximale Anzahl der Verbindungsanforderungen in der Warteschlange, die für einen Webdienst ausstehen können.  Das `connectionLeaseTimeout`\-Attribut beschränkt die Zeit, die ein Client wartet, bevor eine Verbindungsausnahme ausgelöst wird.  Dies ist eine Eigenschaft auf Socketebene, die die maximale Anzahl der in der Warteschlange eingereihten Verbindungsanforderungen steuert, die für einen Webdienst ausstehend sein können.  Wenn ListenBacklog zu niedrig ist, akzeptiert WCF keine Anforderungen mehr und lehnt neue Verbindungen ab, bis der Server einige der vorhandenen Verbindungen in der Warteschlange bestätigt. Der Standardwert ist 16 \* Anzahl von Prozessoren.|  
|portSharingEnabled|Ein boolescher Wert, der angibt, ob die TCP\-Anschlussfreigabe für diese Verbindung aktiviert ist.  Wenn dies `false` ist, verwendet jede Bindung ihren eigenen Anschluss.  Die Standardeinstellung ist `false`.<br /><br /> Diese Einstellung ist nur für Dienste relevant.  Auf Clients hat dies keine Auswirkung.<br /><br /> Bei Verwendung dieser Einstellung muss der Windows Communication Foundation \(WCF\)\-TCP\-Anschlussfreigabedienst aktiviert werden, indem der Starttyp auf Manuell oder Automatisch gesetzt wird.|  
|teredoEnabled|Ein boolescher Wert, der angibt, ob das Teredo\-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird.  Die Standardeinstellung ist `false`.<br /><br /> Mit dieser Eigenschaft wird das Teredo\-Protokoll für das zugrunde liegende TCP\-Socket aktiviert.  Weitere Informationen finden Sie unter [Teredo – Übersicht](http://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Diese Eigenschaft kann nur unter [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] und unter [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)] verwendet werden.  [!INCLUDE[wv](../../../../../includes/wv-md.md)] verfügt über eine computerweite Konfigurationsoption für Teredo, sodass diese Eigenschaft bei der Ausführung von Vista ignoriert wird.  Um das Teredo\-Protokoll verwenden zu können, müssen der Client und die Dienstcomputer über den IPv6\-Stapel von Microsoft verfügen und ordnungsgemäß konfiguriert sein.  Weitere Informationen zum Konfigurieren von Teredo finden Sie unter [Teredo – Übersicht](http://go.microsoft.com/fwlink/?LinkId=95339).  Weitere Informationen finden Sie unter [Windows Server 2003 Technology Centers](http://go.microsoft.com/fwlink/?LinkId=49888).|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Dieser Transport verwendet URIs im Format "net.tcp:\/\/hostname:port\/path".  Andere URI\-Komponenten sind optional.  
  
 Das `tcpTransport`\-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das TCP\-Transportprotokoll implementiert.  Dieser Transport ist für die Kommunikation zwischen WCF und WCF optimiert.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>   
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)