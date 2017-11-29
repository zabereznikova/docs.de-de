---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c89acb38678879f882d8bb2a2b5277b555a1eb26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltexposedmethodgt"></a>&lt;exposedMethod&gt;
Stellt eine COM+-Methode dar, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.  
  
 \<System. ServiceModel >  
\<ComContracts >  
\<ComContract >  
\<Methoden >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine Zeichenfolge, die die COM+-Methode enthält, die verfügbar gemacht wird, wenn die Schnittstelle für eine COM+-Komponente als Webdienst bereitgestellt wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ExposedMethods >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Eine Auflistung von [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.|  
  
## <a name="remarks"></a>Hinweise  
 Mit dem Konfigurationstool für die COM+-Integration (ComSvcConfig.exe) können dem erzeugten Dienstvertrag spezifische Methoden aus einer COM-Schnittstelle hinzugefügt werden.  
  
 Beispielsweise können Sie dem erzeugten Dienstvertrag mit dem folgenden Befehl die drei benannten Methoden aus der `IFinances`-COM-Schnittstelle in der `ItemOrders`.Financial-Komponente hinzufügen.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Wenn Sie auch die ComSvcConfig.exe ausführen, wird die folgende Dienstvertrag mit den zuvor erwähnten Methoden als [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 Bei Initialisierung des Diensts wird der Laufzeit versucht, einen Dienstvertrag zu generieren, durch Reflektieren über und nur die in der Liste der enthaltenen Methoden hinzufügen [ \<ExposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) Elemente. Eine Ablaufverfolgung wird für jede Schnittstellenmethode erzeugt, die nicht im Dienstvertrag enthalten ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [\<ComContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [Integrieren von COM+-Anwendungen](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
