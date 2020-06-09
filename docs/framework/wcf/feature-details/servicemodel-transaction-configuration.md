---
title: ServiceModel-Transaktionskonfiguration
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 1d04a7bb756cccb33b436c1f57decc0249764828
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600334"
---
# <a name="servicemodel-transaction-configuration"></a>ServiceModel-Transaktionskonfiguration
Windows Communication Foundation (WCF) stellt drei Attribute zum Konfigurieren von Transaktionen für einen Dienst bereit: `transactionFlow` , `transactionProtocol` und `transactionTimeout` .  
  
## <a name="configuring-transactionflow"></a>Konfigurieren des transactionFlow-Attributs  
 Die meisten der vordefinierten Bindungen, die WCF bereitstellt, enthalten die `transactionFlow` `transactionProtocol` Attribute und, sodass Sie die Bindung so konfigurieren können, dass eingehende Transaktionen für einen bestimmten Endpunkt unter Verwendung eines bestimmten Transaktions Fluss Protokolls akzeptiert werden. Darüber hinaus können Sie mit dem `transactionFlow`-Element und dessen `transactionProtocol`-Attribut Ihre eigene Bindung erstellen. Weitere Informationen zum Festlegen der Konfigurationselemente finden Sie unter [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) und [WCF-Konfigurations Schema](../../configure-apps/file-schema/wcf/index.md).  
  
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
 Sie können das- `transactionTimeout` Attribut für den WCF-Dienst im- `behavior` Element der Konfigurationsdatei konfigurieren. Im folgenden Codebeispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [WCF-Konfigurationsschema](../../configure-apps/file-schema/wcf/index.md)
