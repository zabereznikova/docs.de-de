---
title: "&lt;callbackDebug&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;callbackDebug&gt;
Legt Dienstdebugging für ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Rückrufobjekt fest.  
  
## Syntax  
  
```  
  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## Typ  
 `Type`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`includeExceptionDetailInFaults`|Ein Wert, der angibt, ob Clientcallback\-Objekte verwaltete Ausnahmeinformationen in SOAP\-Fehlern zurück an den Dienst geben.<br /><br /> Wenn Sie dieses Attribut programmgesteuert auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen eines Clientcallback\-Objekts zurück an den Dienst zu Debuggingzwecken aktivieren. **Caution:**  Verwaltete Ausnahmeinformationen an Clients zurückzugeben, kann ein Sicherheitsrisiko darstellen.  Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>   
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>