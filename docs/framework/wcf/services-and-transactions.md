---
title: Dienste und Transaktionen
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 4c59b83448f5a2c448843c12dae99c442441441f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143277"
---
# <a name="services-and-transactions"></a><span data-ttu-id="12208-102">Dienste und Transaktionen</span><span class="sxs-lookup"><span data-stu-id="12208-102">Services and Transactions</span></span>
<span data-ttu-id="12208-103">Windows Communication Foundation (WCF)-Anwendungen können eine Transaktion innerhalb eines Clients initiieren und die Transaktion innerhalb des Dienstvorgangs koordinieren.</span><span class="sxs-lookup"><span data-stu-id="12208-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="12208-104">Clients können eine Transaktion initiieren und mehrere Dienstvorgänge aufrufen und sicherstellen, dass für die Dienstvorgänge entweder ein Commit oder ein Rollback als einzelne Einheit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="12208-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="12208-105">Sie können das Transaktionsverhalten im Dienstvertrag aktivieren, indem Sie ein <xref:System.ServiceModel.ServiceBehaviorAttribute> festlegen und die <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>-Eigenschaft und die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft für Dienstvorgänge, die Clienttransaktionen benötigen, festlegen.</span><span class="sxs-lookup"><span data-stu-id="12208-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="12208-106">Der <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>-Parameter legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine unbehandelten Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="12208-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="12208-107">Weitere Informationen zu diesen Attributen finden Sie unter [ServiceModel-Transaktionsattribute](./feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="12208-107">For more information about these attributes, see [ServiceModel Transaction Attributes](./feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="12208-108">Die Aufgaben (z. B. die Protokollierung von Datenbankupdates), die in den Dienstvorgängen ausgeführt und von einem Ressourcenmanager verwaltet werden, sind Teil der Clienttransaktionen.</span><span class="sxs-lookup"><span data-stu-id="12208-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="12208-109">Das folgende Beispiel veranschaulicht die Nutzung der <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribute und <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribute bei der Steuerung des Transaktionsverhalten aufseiten des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="12208-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 <span data-ttu-id="12208-110">Sie können Transaktionen und Denkfluss aktivieren, indem Sie die Client- und Dienstbindungen so konfigurieren, `true`dass das WS-AtomicTransaction-Protokoll verwendet wird, und das [ \<transactionFlow->-Element](../configure-apps/file-schema/wcf/transactionflow.md) auf festlegen, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="12208-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
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
  
 <span data-ttu-id="12208-111">Clients können eine Transaktion starten, indem Sie <xref:System.Transactions.TransactionScope> erstellen und Dienstvorgänge im Transaktionsumfang aufrufen.</span><span class="sxs-lookup"><span data-stu-id="12208-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="12208-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12208-112">See also</span></span>

- [<span data-ttu-id="12208-113">Transaktionsunterstützung in System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="12208-113">Transactional Support in System.ServiceModel</span></span>](./feature-details/transactional-support-in-system-servicemodel.md)
- [<span data-ttu-id="12208-114">Transaktionsmodelle</span><span class="sxs-lookup"><span data-stu-id="12208-114">Transaction Models</span></span>](./feature-details/transaction-models.md)
- [<span data-ttu-id="12208-115">WS-Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="12208-115">WS Transaction Flow</span></span>](./samples/ws-transaction-flow.md)
