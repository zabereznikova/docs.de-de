---
title: "&lt;mexHttpsBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;mexHttpsBinding&gt;
Gibt die Einstellungen für eine Bindung an, die für den WS\-MetadataExchange\-Nachrichtenaustausch \(WS\-MEX\) über HTTPS verwendet wird.  
  
## Syntax  
  
```  
  
<mexHttpsBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan">  
   </binding>  
</mexHttpsBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`closeTimeout`|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|`name`|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält.  Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird.  Jede Bindung hat ein `name`\-Attribut und ein `namespace`\-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.  Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor.  Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.  Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhalten finden Sie unter [Vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:10:00.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>\-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt.  Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein.  Der Standardwert ist 00:01:00.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindungen\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## Hinweise  
 Diese Bindung ist im Grunde eine `WSHttpBinding`\-Bindung, die mit Zertifikaten Sicherheit auf Transportebene unterstützt.  Weitere Informationen zum Konfigurieren und Verwenden eines Metadatenendpunkts finden Sie unter [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS\-Metadatenaustausch\-Bindung](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [Vorgehensweise: Abrufen von Metadaten über eine Nicht\-MEX\-Bindung](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md) und im Beispiel [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>   
 <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)   
 [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS\-Metadatenaustausch\-Bindung](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)   
 [Vorgehensweise: Abrufen von Metadaten über eine Nicht\-MEX\-Bindung](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)   
 [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)   
 [Metadaten](../../../../../docs/framework/wcf/feature-details/metadata.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)