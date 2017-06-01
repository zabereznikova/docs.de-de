---
title: "&lt;exposedMethod&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;exposedMethod&gt;
Stellt eine COM\+\-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM\+\-Komponente als Webdienst bereitgestellt wird.  
  
## Syntax  
  
```  
  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Name|Eine Zeichenfolge, die die COM\+\-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM\+\-Komponente als Webdienst bereitgestellt wird.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<exposedMethods\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Eine Auflistung von [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)\-Elementen.|  
  
## Hinweise  
 Mit dem Konfigurationstool für die COM\+\-Integration \(ComSvcConfig.exe\) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM\-Schnittstelle hinzugefügt werden.  
  
 Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`\-COM\-Schnittstelle in der `ItemOrders`.Financial\-Komponente hinzufügen.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Wenn Sie außerdem das Tool ComSvcConfig.exe ausführen, wird der folgende Dienstvertrag mit den bereits erwähnten Methoden in Form von [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)\-Elementen erzeugt.  
  
```  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 Bei der Initialisierung des Diensts wird von der Laufzeit versucht, durch Reflektieren über den Methoden und durch Hinzufügen der Methoden, die in der Liste der [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)\-Elemente aufgeführt sind, einen Dienstvertrag zu erzeugen.  Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>   
 <xref:System.ServiceModel.Configuration.ComMethodElement>   
 [\<comContracts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)   
 [Integrieren von COM\+\-Anwendungen](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Vorgehensweise: Konfigurieren von COM\+\-Diensteinstellungen](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)