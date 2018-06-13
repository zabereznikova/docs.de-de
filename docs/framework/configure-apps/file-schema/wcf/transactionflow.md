---
title: '&lt;TransactionFlow-Protokolls&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c708098676e5634281e29c17639304a1a9cf5afe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748710"
---
# <a name="lttransactionflowgt"></a>&lt;TransactionFlow-Protokolls&gt;
Gibt die Transaktionsflussunterstützung für die benutzerdefinierte Bindung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
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
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Element können Sie den eingehenden Transaktionsfluss in den Bindungseinstellungen eines Endpunkts aktivieren oder deaktivieren und das gewünschte Protokollformat für eingehende Transaktionen angeben. Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) und [Transaktionsfluss aktivieren](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
>  Bei Verwendung des `OleTransactions`-Protokolls für den Transaktionsfluss von Endpunkt zu Endpunkt kann das Transaktionstimeout verloren gehen, wenn der Zielendpunkt mit einem anderen Protokoll als `OleTransactions` versucht, die Transaktion erneut weiterzugeben. Dies kann dazu führen, dass alle Knoten auf den unteren Ebenen nach dem OleTransactions-Hop später als erwartet das Timeout erreichen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [ServiceModel-Transaktionskonfiguration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [Aktivieren des Transaktionsdatenflusses](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
