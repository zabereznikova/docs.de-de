---
title: "&lt;transactionFlow&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;transactionFlow&gt;
Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.  
  
## Syntax  
  
```  
  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|transactionProtocol|Gibt das zu verwendende Transaktionsprotokoll an.  Folgende Werte sind gültig:<br /><br /> -   OleTransactions<br />-   WSAtomicTransactionOctober2004<br /><br /> Der Standardwert ist OleTransactions.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Bindung\>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## Hinweise  
 Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben.  Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel\-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Aktivieren des Transaktionsflusses](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Bei Verwendung des `OleTransactions`\-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben.  Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions\-Hop später als erwartet das Timeout erreichen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>   
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [ServiceModel\-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)   
 [Aktivieren des Transaktionsflusses](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)