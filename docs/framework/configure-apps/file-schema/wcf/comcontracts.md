---
title: "&lt;comContracts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;comContracts&gt;
Der `comContracts`\-Konfigurationsabschnitt enthält Elemente, mit denen Sie verschiedene Eigenschaften eines COM\+\-Integrationsdienstvertrags angeben können.  
  
## Angeben von Namespace und Vertrag  
 Die COM\+\-Integrationsdienstverträge sind aktuell auf den Namespace 'http:\/\/tempuri.org' beschränkt, und der Vertragsname wird von der unterstützenden COM\-Schnittstelle abgeleitet.  Sie können Alternativen aber angeben, indem Sie den Abschnitt `comContracts` in der Konfigurationsdatei verwenden.  
  
 Sie können z.&\#160;B. folgende Konfiguration zum Angeben des Namespaces und Namens des Dienstvertrags sowie als Option zum Erzwingen sitzungsbasierter Bindungen verwenden.  
  
```  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 Wenn der Dienst initialisiert wird, werden die angegebenen Namespaces und Vertragsnamen auf die generierten Dienstbeschreibungen angewendet.  
  
 Wenn dieser Abschnitt leer ist, wendet die Dienstinitialisierung einen standardmäßigen Namespace und Vertragsnamen aus der unterstützenden COM\-Schnittstellen\-ID an.  
  
 Zusätzlich können Sie das [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)\-Element zum Angeben von COM\+\-Methoden verwenden, die verfügbar gemacht werden, wenn die COM\+\-Komponente als Webdienst bereitgestellt wird.  Sie können außerdem [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) zum Angeben von dauerhaften Typen in der Integration verwenden.  Schließlich können Sie [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) zum Angeben von benutzerdefinierten Typen \(UDT\) verwenden, die in den Dienstvertrag einbezogen werden sollen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>   
 <xref:System.ServiceModel.Configuration.ComContractElement>   
 [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)   
 [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)   
 [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)   
 [\<comContract\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)   
 [Integrieren von COM\+\-Anwendungen](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Vorgehensweise: Konfigurieren von COM\+\-Diensteinstellungen](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)