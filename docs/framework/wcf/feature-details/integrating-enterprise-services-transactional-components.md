---
title: Integrieren von Enterprise Services-Transaktionskomponenten
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 5914f76639adc3ff569a3bfb8d6eb1db14313e76
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76211935"
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="a44ff-102">Integrieren von Enterprise Services-Transaktionskomponenten</span><span class="sxs-lookup"><span data-stu-id="a44ff-102">Integrating Enterprise Services Transactional Components</span></span>

<span data-ttu-id="a44ff-103">Windows Communication Foundation (WCF) bietet einen automatischen Mechanismus zum Integrieren in Enterprise Services (siehe [integrieren in com+-Anwendungen](integrating-with-com-plus-applications.md)).</span><span class="sxs-lookup"><span data-stu-id="a44ff-103">Windows Communication Foundation (WCF) provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="a44ff-104">Möglicherweise benötigen Sie die Flexibilität zur Entwicklung von Diensten, die von Enterprise Services gehostete Transaktionskomponenten intern verwenden.</span><span class="sxs-lookup"><span data-stu-id="a44ff-104">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="a44ff-105">Da die WCF-Transaktions Funktion auf der <xref:System.Transactions>-Infrastruktur basiert, ist der Prozess zum Integrieren von Enterprise Services in WCF identisch mit dem zum Angeben von Interoperabilität zwischen <xref:System.Transactions> und Enterprise Services, wie unter [Interoperabilität mit Enterprise Services und com+-Transaktionen](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85))beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a44ff-105">Because the WCF Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with WCF is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85)).</span></span>  
  
 <span data-ttu-id="a44ff-106">Um das gewünschte Maß an Interoperabilität zwischen der eingehenden übergebenden Transaktion und der COM+-Kontexttransaktion zu erzielen, muss die Dienstimplementierung eine <xref:System.Transactions.TransactionScope>-Instanz erstellen und den entsprechenden Wert der <xref:System.Transactions.EnterpriseServicesInteropOption>-Enumeration verwenden.</span><span class="sxs-lookup"><span data-stu-id="a44ff-106">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="a44ff-107">Integrieren von Enterprise Services mit einem Dienstvorgang</span><span class="sxs-lookup"><span data-stu-id="a44ff-107">Integrating Enterprise Services with a Service Operation</span></span>  
 <span data-ttu-id="a44ff-108">Der folgende Code veranschaulicht einen Vorgang mit zugelassenem Transaktionsfluss, der einen <xref:System.Transactions.TransactionScope> mit der <xref:System.Transactions.EnterpriseServicesInteropOption.Full>-Option erstellt.</span><span class="sxs-lookup"><span data-stu-id="a44ff-108">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="a44ff-109">Die folgenden Bedingungen sind in diesem Szenario gültig:</span><span class="sxs-lookup"><span data-stu-id="a44ff-109">The following conditions apply in this scenario:</span></span>  
  
- <span data-ttu-id="a44ff-110">Wenn der Client eine Transaktion übergibt, wird der Vorgang, einschließlich des Aufrufs der Enterprise Services-Komponente, innerhalb des Umfangs dieser Transaktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a44ff-110">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="a44ff-111">Mit <xref:System.Transactions.EnterpriseServicesInteropOption.Full> wird sichergestellt, dass die Transaktion mit dem <xref:System.EnterpriseServices>-Kontext synchronisiert wird. Dies bedeutet, dass die Ambient-Transaktion für <xref:System.Transactions> und <xref:System.EnterpriseServices> identisch ist.</span><span class="sxs-lookup"><span data-stu-id="a44ff-111">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
- <span data-ttu-id="a44ff-112">Wenn der Client keine Transaktion übergibt, wird durch Festlegen von <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> auf `true` ein neuer Transaktionsumfang für den Vorgang erstellt.</span><span class="sxs-lookup"><span data-stu-id="a44ff-112">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="a44ff-113">Auf ähnliche Weise wird mit <xref:System.Transactions.EnterpriseServicesInteropOption.Full> sichergestellt, dass die Transaktion des Vorgangs mit der Transaktion übereinstimmt, die innerhalb des Kontexts der <xref:System.EnterpriseServices>-Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a44ff-113">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="a44ff-114">Alle zusätzlichen Methodenaufrufe treten auch innerhalb des Transaktionsumfangs des gleichen Vorgangs auf.</span><span class="sxs-lookup"><span data-stu-id="a44ff-114">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
```csharp
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services   
         // component   
  
         // Call UpdateOtherCustomerData method on an Enterprise   
         // Services component   
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 <span data-ttu-id="a44ff-115">Wenn keine Synchronisierung zwischen der aktuellen Transaktion eines Vorgangs und den Aufrufen für die Transaktionskomponenten von Enterprise Services erforderlich ist, verwenden Sie die <xref:System.Transactions.EnterpriseServicesInteropOption.None>-Option zum Instanziieren der <xref:System.Transactions.TransactionScope>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="a44ff-115">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="a44ff-116">Integrieren von Enterprise Services mit einem Client</span><span class="sxs-lookup"><span data-stu-id="a44ff-116">Integrating Enterprise Services with a Client</span></span>  
 <span data-ttu-id="a44ff-117">Der folgende Code veranschaulicht Clientcode, der eine <xref:System.Transactions.TransactionScope>-Instanz mit der <xref:System.Transactions.EnterpriseServicesInteropOption.Full>-Einstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a44ff-117">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="a44ff-118">In diesem Szenario treten Aufrufe für Dienstvorgänge, die den Transaktionsfluss unterstützen, innerhalb des Umfangs derselben Transaktion auf wie die Aufrufe für Enterprise Services-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="a44ff-118">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
```csharp
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services   
        // component   
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and   
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a44ff-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a44ff-119">See also</span></span>

- [<span data-ttu-id="a44ff-120">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a44ff-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a44ff-121">Integrieren von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a44ff-121">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
