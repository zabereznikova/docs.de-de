---
title: ServiceModel-Transaktionskonfiguration
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: d5bb81c618e3b27df32763948dbe56c9b37995e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747705"
---
# <a name="servicemodel-transaction-configuration"></a>ServiceModel-Transaktionskonfiguration
Windows Communication Foundation (WCF) bietet drei Attribute zum Konfigurieren von Transaktionen für einen Dienst: `transactionFlow`, `transactionProtocol`, und `transactionTimeout`.  
  
## <a name="configuring-transactionflow"></a>Konfigurieren des transactionFlow-Attributs  
 Die vordefinierten Bindungen, WCF bietet enthalten, die meisten der `transactionFlow` und `transactionProtocol` Attribute, sodass Sie die Bindung für die Annahme eingehender Transaktionen für einen bestimmten Endpunkt mit einem bestimmten transaktionsflussprotokolls konfigurieren können. Darüber hinaus können Sie mit dem `transactionFlow`-Element und dessen `transactionProtocol`-Attribut Ihre eigene Bindung erstellen. Weitere Informationen zum Festlegen der Konfigurationselemente finden Sie unter [ \<Bindung >](../../../../docs/framework/misc/binding.md) und [WCF-Konfigurationsschema](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
 Das `transactionFlow`-Attribut gibt an, ob der Transaktionsfluss für Dienstendpunkte aktiviert ist, die die Bindung verwenden.  
  
## <a name="configuring-transactionprotocol"></a>Konfigurieren des transactionProtocol-Attributs  
 Das `transactionProtocol`-Attribut gibt das Transaktionsprotokoll an, das für die Dienstendpunkte verwendet werden soll, die die Bindung verwenden.  
  
 Nachstehend finden Sie ein Beispiel für einen Konfigurationsabschnitt, mit dem die angegebene Bindung so konfiguriert wird, dass der Transaktionsfluss unterstützt und das WS-Atomic-Transaktionsprotokoll verwendet wird.  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"   
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"   
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a>Konfigurieren des transactionTimeout-Attributs  
 Sie können konfigurieren, die `transactionTimeout` -Attribut für den WCF-Dienst in der `behavior` Element der Konfigurationsdatei. Im folgenden Codebeispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 Das `transactionTimeout`-Attribut legt den Zeitraum fest, innerhalb dessen eine neue, für den Dienst erstellte Transaktion abgeschlossen sein muss. Dieses Attribut wird als <xref:System.Transactions.TransactionScope>-Timeout für alle Vorgänge verwendet, die zu einer neuen Transaktion führen. Wird <xref:System.ServiceModel.OperationBehaviorAttribute> angewendet, wird die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft auf `true` gesetzt.  
  
 Der Timeout gibt den Zeitraum von der Erstellung der Transaktion bis zum Abschluss von Phase 1 im Zweiphasencommit-Protokoll an.  
  
 Wenn dieses Attribut in einem `service`-Konfigurationsabschnitt festgelegt wird, sollten Sie mindestens eine Methode des zugehörigen Diensts mit <xref:System.ServiceModel.OperationBehaviorAttribute>, in dem die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft auf `true` gesetzt ist, anwenden.  
  
 Beachten Sie, dass als Timeoutwert der kleinere Wert von dieser `transactionTimeout`-Konfigurationseinstellung und allen <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>-Eigenschaften verwendet wird.  
  
## <a name="see-also"></a>Siehe auch

- [\<binding>](../../../../docs/framework/misc/binding.md)
- [WCF Configuration Schema (Schema zur WCF-Konfiguration)](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)
