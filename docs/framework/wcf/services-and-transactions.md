---
title: Dienste und Transaktionen
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 85792584660bd742ad3d313bf04ef1ce88bddcc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33504318"
---
# <a name="services-and-transactions"></a><span data-ttu-id="19531-102">Dienste und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="19531-102">Services and Transactions</span></span>
<span data-ttu-id="19531-103">Windows Communication Foundation (WCF)-Anwendungen können eine Transaktion von einem Client initiieren und die Transaktion im Dienstvorgang koordinieren.</span><span class="sxs-lookup"><span data-stu-id="19531-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="19531-104">Clients können eine Transaktion initiieren und mehrere Dienstvorgänge aufrufen und sicherstellen, dass für die Dienstvorgänge entweder ein Commit oder ein Rollback als einzelne Einheit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="19531-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="19531-105">Sie können das Transaktionsverhalten im Dienstvertrag aktivieren, indem Sie ein <xref:System.ServiceModel.ServiceBehaviorAttribute> festlegen und die <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>-Eigenschaft und die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft für Dienstvorgänge, die Clienttransaktionen benötigen, festlegen.</span><span class="sxs-lookup"><span data-stu-id="19531-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="19531-106">Der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Parameter legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine unbehandelten Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="19531-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="19531-107">Weitere Informationen zu diesen Attributen finden Sie unter [ServiceModel-Transaktionsattribute](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="19531-107">For more information about these attributes, see [ServiceModel Transaction Attributes](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="19531-108">Die Aufgaben (z. B. die Protokollierung von Datenbankupdates), die in den Dienstvorgängen ausgeführt und von einem Ressourcenmanager verwaltet werden, sind Teil der Clienttransaktionen.</span><span class="sxs-lookup"><span data-stu-id="19531-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="19531-109">Das folgende Beispiel veranschaulicht die Nutzung der <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribute und <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribute bei der Steuerung des Transaktionsverhalten aufseiten des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="19531-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 <span data-ttu-id="19531-110">Können Sie Transaktionen aktivieren und Transaktion unter Konfigurieren des Clients und -service-Bindungen verwendet die WS-AtomicTransaction-Protokoll und das Festlegen der [ \<TransactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) Element `true`(siehe) in der folgenden Beispielkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="19531-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"   
          binding="netTcpBinding"   
          bindingConfiguration="netTcpBindingWSAT"   
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="19531-111">Clients können eine Transaktion starten, indem Sie <xref:System.Transactions.TransactionScope> erstellen und Dienstvorgänge im Transaktionsumfang aufrufen.</span><span class="sxs-lookup"><span data-stu-id="19531-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="19531-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19531-112">See Also</span></span>  
 [<span data-ttu-id="19531-113">Transaktionsunterstützung in System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19531-113">Transactional Support in System.ServiceModel</span></span>](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [<span data-ttu-id="19531-114">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="19531-114">Transaction Models</span></span>](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [<span data-ttu-id="19531-115">WS-Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="19531-115">WS Transaction Flow</span></span>](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
