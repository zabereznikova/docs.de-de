---
title: ServiceModel-Transaktionskonfiguration
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: 27deaf38a8809b8a7fca560cc6783bd24dc43686
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242889"
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="8638e-102">ServiceModel-Transaktionskonfiguration</span><span class="sxs-lookup"><span data-stu-id="8638e-102">ServiceModel Transaction Configuration</span></span>

<span data-ttu-id="8638e-103">Windows Communication Foundation (WCF) stellt drei Attribute zum Konfigurieren von Transaktionen für einen Dienst bereit: `transactionFlow` , `transactionProtocol` und `transactionTimeout` .</span><span class="sxs-lookup"><span data-stu-id="8638e-103">Windows Communication Foundation (WCF) provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="8638e-104">Konfigurieren des transactionFlow-Attributs</span><span class="sxs-lookup"><span data-stu-id="8638e-104">Configuring transactionFlow</span></span>  

 <span data-ttu-id="8638e-105">Die meisten der vordefinierten Bindungen, die WCF bereitstellt, enthalten die `transactionFlow` `transactionProtocol` Attribute und, sodass Sie die Bindung so konfigurieren können, dass eingehende Transaktionen für einen bestimmten Endpunkt unter Verwendung eines bestimmten Transaktions Fluss Protokolls akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="8638e-105">Most of the predefined bindings WCF provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="8638e-106">Darüber hinaus können Sie mit dem `transactionFlow`-Element und dessen `transactionProtocol`-Attribut Ihre eigene Bindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="8638e-106">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> <span data-ttu-id="8638e-107">Weitere Informationen zum Festlegen der Konfigurationselemente finden Sie unter [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) und [WCF-Konfigurations Schema](../../configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="8638e-107">For more information about setting the configuration elements, see [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) and [WCF Configuration Schema](../../configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="8638e-108">Das `transactionFlow`-Attribut gibt an, ob der Transaktionsfluss für Dienstendpunkte aktiviert ist, die die Bindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8638e-108">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="8638e-109">Konfigurieren des transactionProtocol-Attributs</span><span class="sxs-lookup"><span data-stu-id="8638e-109">Configuring transactionProtocol</span></span>  

 <span data-ttu-id="8638e-110">Das `transactionProtocol`-Attribut gibt das Transaktionsprotokoll an, das für die Dienstendpunkte verwendet werden soll, die die Bindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8638e-110">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="8638e-111">Nachstehend finden Sie ein Beispiel für einen Konfigurationsabschnitt, mit dem die angegebene Bindung so konfiguriert wird, dass der Transaktionsfluss unterstützt und das WS-Atomic-Transaktionsprotokoll verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8638e-111">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
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
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="8638e-112">Konfigurieren des transactionTimeout-Attributs</span><span class="sxs-lookup"><span data-stu-id="8638e-112">Configuring transactionTimeout</span></span>  

 <span data-ttu-id="8638e-113">Sie können das- `transactionTimeout` Attribut für den WCF-Dienst im- `behavior` Element der Konfigurationsdatei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8638e-113">You can configure the `transactionTimeout` attribute for your WCF service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="8638e-114">Im folgenden Codebeispiel wird die hierfür erforderliche Vorgehensweise veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="8638e-114">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="8638e-115">Das `transactionTimeout`-Attribut legt den Zeitraum fest, innerhalb dessen eine neue, für den Dienst erstellte Transaktion abgeschlossen sein muss.</span><span class="sxs-lookup"><span data-stu-id="8638e-115">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="8638e-116">Dieses Attribut wird als <xref:System.Transactions.TransactionScope>-Timeout für alle Vorgänge verwendet, die zu einer neuen Transaktion führen. Wird <xref:System.ServiceModel.OperationBehaviorAttribute> angewendet, wird die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft auf `true` gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8638e-116">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="8638e-117">Der Timeout gibt den Zeitraum von der Erstellung der Transaktion bis zum Abschluss von Phase 1 im Zweiphasencommit-Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="8638e-117">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="8638e-118">Wenn dieses Attribut in einem `service`-Konfigurationsabschnitt festgelegt wird, sollten Sie mindestens eine Methode des zugehörigen Diensts mit <xref:System.ServiceModel.OperationBehaviorAttribute>, in dem die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft auf `true` gesetzt ist, anwenden.</span><span class="sxs-lookup"><span data-stu-id="8638e-118">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="8638e-119">Beachten Sie, dass als Timeoutwert der kleinere Wert von dieser `transactionTimeout`-Konfigurationseinstellung und allen <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>-Eigenschaften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8638e-119">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8638e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8638e-120">See also</span></span>

- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)
- [<span data-ttu-id="8638e-121">WCF-Konfigurations Schema</span><span class="sxs-lookup"><span data-stu-id="8638e-121">WCF Configuration Schema</span></span>](../../configure-apps/file-schema/wcf/index.md)
