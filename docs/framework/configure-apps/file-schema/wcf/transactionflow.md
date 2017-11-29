---
title: '&lt;TransactionFlow-Protokolls&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8c40b3a79567ccc1ca5a83631253d3ff6ead0f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactionflowgt"></a>&lt;TransactionFlow-Protokolls&gt;
Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.  
  
 \<system.serviceModel >  
\<Bindungen >  
\<CustomBinding >  
\<Binden von >  
\<TransactionFlow >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|transactionProtocol|Gibt das zu verwendende Transaktionsprotokoll an. Folgende Werte sind gültig:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> Der Standardwert ist OleTransactions.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.TransactionProtocol>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Binden von >](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben. Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben. Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [Aktivieren des Transaktionsflusses](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<CustomBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
