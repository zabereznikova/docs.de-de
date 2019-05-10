---
title: WS-Transaktionsfluss
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 8c021e3b3de1dbe000ab328f7a09d79a4bc966fe
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592218"
---
# <a name="ws-transaction-flow"></a><span data-ttu-id="b75b7-102">WS-Transaktionsfluss</span><span class="sxs-lookup"><span data-stu-id="b75b7-102">WS Transaction Flow</span></span>
<span data-ttu-id="b75b7-103">In diesem Beispiel werden die Verwendung einer clientkoordinierten Transaktion und die Client- und Serveroptionen für den Transaktionsfluss unter Verwendung des WS-Atomic-Transaktionsprotokolls oder des OleTransactions-Protokolls erläutert.</span><span class="sxs-lookup"><span data-stu-id="b75b7-103">This sample demonstrates the use of a client-coordinated transaction and the client and server options for transaction flow using either the WS-Atomic Transaction or OleTransactions protocol.</span></span> <span data-ttu-id="b75b7-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert, aber die Vorgänge zum Veranschaulichen der Verwendung von attributiert sind die `TransactionFlowAttribute` mit der **TransactionFlowOption** Enumeration, um zu bestimmen, in welchem Umfang der Transaktionsfluss aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b75b7-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service but the operations are attributed to demonstrate the use of the `TransactionFlowAttribute` with the **TransactionFlowOption** enumeration to determine to what degree transaction flow is enabled.</span></span> <span data-ttu-id="b75b7-105">Innerhalb des Bereichs des Transaktionsflusses wird ein Protokoll der angeforderten Vorgänge in eine Datenbank geschrieben. Dieses bleibt dort erhalten, bis die clientkoordinierte Transaktion fertiggestellt wurde. Wenn die Clienttransaktion nicht fertiggestellt wird, stellt die Webdiensttransaktion sicher, dass die entsprechenden Aktualisierungen der Datenbank nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-105">Within the scope of the flowed transaction, a log of the requested operations is written to a database and persists until the client coordinated transaction has completed - if the client transaction does not complete, the Web service transaction ensures that the appropriate updates to the database are not committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b75b7-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="b75b7-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b75b7-107">Nach der Initiierung einer Verbindung zu dem Dienst und einer Transaktion greift der Client auf mehrere Dienstvorgänge zu.</span><span class="sxs-lookup"><span data-stu-id="b75b7-107">After initiating a connection to the service and a transaction, the client accesses several service operations.</span></span> <span data-ttu-id="b75b7-108">Der Vertrag für den Dienst ist folgendermaßen definiert, dabei veranschaulicht jeder der Vorgänge eine andere Einstellung für die `TransactionFlowOption`.</span><span class="sxs-lookup"><span data-stu-id="b75b7-108">The contract for the service is defined as follows with each of the operations demonstrating a different setting for the `TransactionFlowOption`.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);   
}  
```

 <span data-ttu-id="b75b7-109">Auf diese Weise werden die Vorgänge in der Reihenfolge, in der sie verarbeitet werden sollten, definiert:</span><span class="sxs-lookup"><span data-stu-id="b75b7-109">This defines the operations in the order they are to be processed:</span></span>  
  
- <span data-ttu-id="b75b7-110">Eine `Add`-Vorgangsanforderung muss einen Transaktionsfluss beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-110">An `Add` operation request must include a flowed transaction.</span></span>  
  
- <span data-ttu-id="b75b7-111">Eine `Subtract`-Vorgangsanforderung kann einen Transaktionsfluss beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-111">A `Subtract` operation request may include a flowed transaction.</span></span>  
  
- <span data-ttu-id="b75b7-112">Eine `Multiply`-Vorgangsanforderung darf keinen Transaktionsfluss durch die explizite NotAllowed-Einstellung beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-112">A `Multiply` operation request must not include a flowed transaction through the explicit NotAllowed setting.</span></span>  
  
- <span data-ttu-id="b75b7-113">Eine `Divide`-Vorgangsanforderung darf keinen Transaktionsfluss durch die Auslassung eines `TransactionFlow`-Attributs beinhalten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-113">A `Divide` operation request must not include a flowed transaction through the omission of a `TransactionFlow` attribute.</span></span>  
  
 <span data-ttu-id="b75b7-114">Zum Aktivieren des Transaktionsflusses, Bindungen, bei denen die [ \<TransactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) -Eigenschaft aktiviert ist, muss zusätzlich zu den entsprechenden Vorgangsattributen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-114">To enable transaction flow, bindings with the [\<transactionFlow>](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) property enabled must be used in addition to the appropriate operation attributes.</span></span> <span data-ttu-id="b75b7-115">In diesem Beispiel macht die Dienstkonfiguration zusätzlich zu einem Metadatenaustausch-Endpunkt einen TCP-Endpunkt und einen HTTP-Endpunkt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b75b7-115">In this sample, the service's configuration exposes a TCP endpoint and an HTTP endpoint in addition to a Metadata Exchange endpoint.</span></span> <span data-ttu-id="b75b7-116">Der TCP-Endpunkt und den HTTP-Endpunkt verwenden Sie die folgenden Bindungen, die jeweils die [ \<TransactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) -Eigenschaft aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b75b7-116">The TCP endpoint and the HTTP endpoint use the following bindings, both of which have the [\<transactionFlow>](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) property enabled.</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="b75b7-117">Die vom System bereitgestellte netTcpBinding ermöglicht die Festlegung des transactionProtocol, während die vom System bereitgestellte wsHttpBinding nur das interoperablere WSAtomicTransactionOctober2004-Protokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b75b7-117">The system-provided netTcpBinding allows specification of the transactionProtocol whereas the system-provided wsHttpBinding uses only the more interoperable WSAtomicTransactionOctober2004 protocol.</span></span> <span data-ttu-id="b75b7-118">Die OleTransactions, die Protokoll nur zur Verfügung steht, verwenden von Windows Communication Foundation (WCF)-Clients.</span><span class="sxs-lookup"><span data-stu-id="b75b7-118">The OleTransactions protocol is only available for use by Windows Communication Foundation (WCF) clients.</span></span>  
  
 <span data-ttu-id="b75b7-119">Für die Klasse, die die `ICalculator`-Schnittstelle implementiert, werden alle Methoden mit auf <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> festgelegter `true`-Eigenschaft attributiert.</span><span class="sxs-lookup"><span data-stu-id="b75b7-119">For the class that implements the `ICalculator` interface, all of the methods are attributed with <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property set to `true`.</span></span> <span data-ttu-id="b75b7-120">Diese Einstellung deklariert, dass alle innerhalb der Methode ausgeführten Aktionen innerhalb des Bereichs einer Transaktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-120">This setting declares that all actions taken within the method occur within the scope of a transaction.</span></span> <span data-ttu-id="b75b7-121">In diesem Fall beinhalten die ausgeführten Aktionen auch Aufzeichnung in der Protokolldatenbank.</span><span class="sxs-lookup"><span data-stu-id="b75b7-121">In this case, the actions taken include recording to the log database.</span></span> <span data-ttu-id="b75b7-122">Wenn die Vorgangsanforderung einen Transaktionsfluss beinhaltet, treten die Aktionen innerhalb des Bereichs der eingehenden Transaktion auf, oder es wird automatisch ein neuer Transaktionsbereich erstellt.</span><span class="sxs-lookup"><span data-stu-id="b75b7-122">If the operation request includes a flowed transaction then the actions occur within the scope of the incoming transaction or a new transaction scope is automatically generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b75b7-123">Die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft definiert das Verhalten lokal in Bezug auf die Implementierungen der Dienstmethode und definiert nicht die Fähigkeit des Clients für oder die Anforderung eines Transaktionsflusses.</span><span class="sxs-lookup"><span data-stu-id="b75b7-123">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property defines behavior local to the service method implementations and does not define the client's ability to or requirement for flowing a transaction.</span></span>  

```csharp
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```

 <span data-ttu-id="b75b7-124">Auf dem Client werden die `TransactionFlowOption`-Einstellungen des Diensts für die Vorgänge in der generierten Definition des Clients für die `ICalculator`-Schnittstelle wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b75b7-124">On the client, the service's `TransactionFlowOption` settings on the operations are reflected in the client's generated definition of the `ICalculator` interface.</span></span> <span data-ttu-id="b75b7-125">Außerdem werden die `transactionFlow`-Eigenschaftseinstellungen des Diensts in der Anwendungskonfiguration des Clients wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="b75b7-125">Also, the service's `transactionFlow` property settings are reflected in the client's application configuration.</span></span> <span data-ttu-id="b75b7-126">Der Client kann den Transport und das Protokoll auswählen, indem er den entsprechenden `endpointConfigurationName` auswählt.</span><span class="sxs-lookup"><span data-stu-id="b75b7-126">The client can select the transport and protocol by selecting the appropriate `endpointConfigurationName`.</span></span>  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
>  <span data-ttu-id="b75b7-127">Das beobachtete Verhalten dieses Beispiels ist das gleiche, unabhängig davon, welches Protokoll oder welcher Transport ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="b75b7-127">The observed behavior of this sample is the same no matter which protocol or transport is chosen.</span></span>  
  
 <span data-ttu-id="b75b7-128">Nach der Initiierung der Verbindung zu dem Dienst erstellt der Client einen neuen `TransactionScope` um die Aufrufe der Dienstvorgänge.</span><span class="sxs-lookup"><span data-stu-id="b75b7-128">Having initiated the connection to the service, the client creates a new `TransactionScope` around the calls to the service operations.</span></span>  

```csharp
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```

 <span data-ttu-id="b75b7-129">Die Aufrufe der Vorgänge sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="b75b7-129">The calls to the operations are as follows:</span></span>  
  
- <span data-ttu-id="b75b7-130">Die `Add`-Anforderung übergibt die erforderliche Transaktion an den Dienst, und die Aktionen des Diensts treten innerhalb des Bereichs der Transaktion des Clients auf.</span><span class="sxs-lookup"><span data-stu-id="b75b7-130">The `Add` request flows the required transaction to the service and the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="b75b7-131">Die erste `Subtract`-Anforderung übergibt die zulässige Transaktion ebenfalls an den Dienst, und die Aktionen des Diensts treten erneut innerhalb des Bereichs der Transaktion des Clients auf.</span><span class="sxs-lookup"><span data-stu-id="b75b7-131">The first `Subtract` request also flows the allowed transaction to the service and again the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="b75b7-132">Die zweite `Subtract`-Anforderung wird innerhalb eines neuen Transaktionsbereichs ausgeführt, der mit der `TransactionScopeOption.Suppress`-Option deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="b75b7-132">The second `Subtract` request is performed within a new transaction scope declared with the `TransactionScopeOption.Suppress` option.</span></span> <span data-ttu-id="b75b7-133">Auf diese Weise wird die initiale äußere Transaktion des Clients unterdrückt, und die Anforderung übergibt keine Transaktion an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b75b7-133">This suppresses the client's initial outer transaction and the request does not flow a transaction to the service.</span></span> <span data-ttu-id="b75b7-134">Mithilfe dieses Verfahrens kann ein Client explizit deaktiviert werden, und es wird verhindert, dass eine Transaktion an einen Dienst übergeben wird, wenn diese nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b75b7-134">This approach allows a client to explicitly opt-out of and protect against flowing a transaction to a service when that is not required.</span></span> <span data-ttu-id="b75b7-135">Die Aktionen des Diensts treten innerhalb des Bereichs einer neuen und unverbundenen Transaktion auf.</span><span class="sxs-lookup"><span data-stu-id="b75b7-135">The service's actions occur within the scope of a new and unconnected transaction.</span></span>  
  
- <span data-ttu-id="b75b7-136">Die `Multiply`-Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition der `ICalculator`-Schnittstelle ein <xref:System.ServiceModel.TransactionFlowAttribute> beinhaltet, für das <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b75b7-136">The `Multiply` request does not flow a transaction to the service because the client's generated definition of the `ICalculator` interface includes a <xref:System.ServiceModel.TransactionFlowAttribute> set to <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.</span></span>  
  
- <span data-ttu-id="b75b7-137">Die `Divide`-Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition der `ICalculator`-Schnittstelle wiederum kein `TransactionFlowAttribute` beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="b75b7-137">The `Divide` request does not flow a transaction to the service because again the client's generated definition of the `ICalculator` interface does not include a `TransactionFlowAttribute`.</span></span> <span data-ttu-id="b75b7-138">Die Aktionen des Diensts treten erneut innerhalb des Bereichs einer anderen neuen und unverbundenen Transaktion auf.</span><span class="sxs-lookup"><span data-stu-id="b75b7-138">The service's actions again occur within the scope of another new and unconnected transaction.</span></span>  
  
 <span data-ttu-id="b75b7-139">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b75b7-139">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b75b7-140">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-140">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="b75b7-141">Die Protokollierung der Dienstvorgangsanforderungen wird im Konsolenfenster des Diensts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b75b7-141">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="b75b7-142">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-142">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 <span data-ttu-id="b75b7-143">Nach einer erfolgreichen Ausführung wird der Transaktionsbereich des Clients abgeschlossen, und alle Aktionen innerhalb des Bereichs werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b75b7-143">After a successful execution, the client's transaction scope completes and all actions taken within that scope are committed.</span></span> <span data-ttu-id="b75b7-144">Vor allem werden die erwähnten fünf Datensätze in der Datenbank des Diensts beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-144">Specifically, the noted 5 records are persisted in the service's database.</span></span> <span data-ttu-id="b75b7-145">Die beiden ersten sind innerhalb des Bereichs der Transaktion des Clients aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-145">The first 2 of these have occurred within the scope of the client's transaction.</span></span>  
  
 <span data-ttu-id="b75b7-146">Wenn im `TransactionScope` des Clients eine Ausnahme aufgetreten ist, kann die Transaktion nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-146">If an exception occurred anywhere within the client's `TransactionScope` then the transaction cannot complete.</span></span> <span data-ttu-id="b75b7-147">Dies führt dazu, dass die innerhalb des Bereichs protokollierten Datensätze nicht an die Datenbank übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-147">This causes the records logged within that scope to not be committed to the database.</span></span> <span data-ttu-id="b75b7-148">Dieser Effekt kann beobachtet werden, wenn das Beispiel erneut ausgeführt wird, nachdem der Aufruf zum Abschließen des äußeren `TransactionScope` auskommentiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b75b7-148">This effect can be observed by repeating the sample run after commenting out the call to complete the outer `TransactionScope`.</span></span> <span data-ttu-id="b75b7-149">Bei einer solchen Ausführung werden nur die letzen drei Aktionen protokolliert (die zweite `Subtract`-, die `Multiply`- und die `Divide`-Anforderung), da die Clienttransaktion nicht an diese übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b75b7-149">On such a run, only the last 3 actions (from the second `Subtract`, the `Multiply` and the `Divide` requests) are logged because the client transaction did not flow to those.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b75b7-150">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="b75b7-150">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b75b7-151">Um die C#- oder Visual Basic .NET Version der Lösung zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="b75b7-151">To build the C# or Visual Basic .NET version of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)</span></span>  
  
2. <span data-ttu-id="b75b7-152">Vergewissern Sie sich, dass SQL Server Express Edition oder SQL Server installiert ist. Stellen Sie außerdem sicher, dass die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei des Diensts ordnungsgemäß festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b75b7-152">Ensure that you have installed SQL Server Express Edition or SQL Server, and that the connection string has been correctly set in the service’s application configuration file.</span></span> <span data-ttu-id="b75b7-153">Wenn Sie das Beispiel ohne eine Datenbank ausführen möchten, legen Sie den `usingSql`-Wert in der Anwendungskonfigurationsdatei des Diensts auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="b75b7-153">To run the sample without using a database, set the `usingSql` value in the service’s application configuration file to `false`</span></span>  
  
3. <span data-ttu-id="b75b7-154">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b75b7-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b75b7-155">Aktivieren Sie bei einer computerübergreifenden Konfiguration Distributed Transaction Coordinator entsprechend den nachfolgenden Anweisungen, und aktivieren Sie mit dem Tool WsatConfig.exe aus dem Windows SDK die Netzwerkunterstützung von WCF-Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-155">For cross-machine configuration, enable the Distributed Transaction Coordinator using the instructions below, and use the WsatConfig.exe tool from the Windows SDK to enable WCF Transactions network support.</span></span> <span data-ttu-id="b75b7-156">Finden Sie unter [WS-AtomicTransaction-Unterstützung konfigurieren](https://go.microsoft.com/fwlink/?LinkId=190370) Informationen zum Einrichten von WsatConfig.exe festlegen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-156">See [Configuring WS-Atomic Transaction Support](https://go.microsoft.com/fwlink/?LinkId=190370) for information on setting up WsatConfig.exe.</span></span>  
  
 <span data-ttu-id="b75b7-157">Ob Sie das Beispiel auf demselben Computer oder auf anderen Computern ausführen, müssen Sie der Microsoft Distributed Transaction Coordinator (MSDTC) zum Aktivieren der Netzwerk-Transaktionsfluss und verwenden das Tool WsatConfig.exe die Netzwerkunterstützung von WCF-Transaktionen aktivieren konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b75b7-157">Whether you run the sample on the same computer or on different computers, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable WCF transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a><span data-ttu-id="b75b7-158">So konfigurieren Sie Microsoft Distributed Transaction Coordinator (MSDTC) zum Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="b75b7-158">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample</span></span>  
  
1. <span data-ttu-id="b75b7-159">Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2003 oder Windows XP entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-159">On a service machine running Windows Server 2003 or Windows XP, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="b75b7-160">Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-160">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="b75b7-161">Erweitern Sie **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-161">Expand **Component Services**.</span></span> <span data-ttu-id="b75b7-162">Öffnen der **Computer** Ordner.</span><span class="sxs-lookup"><span data-stu-id="b75b7-162">Open the **Computers** folder.</span></span>  
  
    3. <span data-ttu-id="b75b7-163">Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-163">Right-click **My Computer** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="b75b7-164">Auf der **MSDTC** auf **Sicherheitskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-164">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    5. <span data-ttu-id="b75b7-165">Überprüfen Sie **DTC-Netzwerkzugriff** und **zulassen eingehender**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-165">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    6. <span data-ttu-id="b75b7-166">Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-166">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    7. <span data-ttu-id="b75b7-167">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-167">Click **OK** to close the dialog box.</span></span>  
  
2. <span data-ttu-id="b75b7-168">Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2008 oder Windows Vista entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="b75b7-168">On a service machine running Windows Server 2008 or Windows Vista, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="b75b7-169">Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="b75b7-170">Erweitern Sie **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-170">Expand **Component Services**.</span></span> <span data-ttu-id="b75b7-171">Öffnen der **Computer** Ordner.</span><span class="sxs-lookup"><span data-stu-id="b75b7-171">Open the **Computers** folder.</span></span> <span data-ttu-id="b75b7-172">Wählen Sie **Distributed Transaction Coordinator**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-172">Select **Distributed Transaction Coordinator**.</span></span>  
  
    3. <span data-ttu-id="b75b7-173">Mit der rechten Maustaste **Distributed Transaction Coordinator** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-173">Right-click **DTC Coordinator** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="b75b7-174">Auf der **Sicherheit** Registerkarte **DTC-Netzwerkzugriff** und **Allow Inbound**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-174">On the **Security** tab, check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5. <span data-ttu-id="b75b7-175">Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-175">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="b75b7-176">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-176">Click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="b75b7-177">Konfigurieren Sie auf dem Clientcomputer MSDTC zum Zulassen von ausgehenden Netzwerktransaktionen:</span><span class="sxs-lookup"><span data-stu-id="b75b7-177">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1. <span data-ttu-id="b75b7-178">Von der **starten** Menü navigieren Sie zu `Control Panel`, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-178">From the **Start** menu, navigate to `Control Panel`, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="b75b7-179">Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-179">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3. <span data-ttu-id="b75b7-180">Auf der **MSDTC** auf **Sicherheitskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-180">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4. <span data-ttu-id="b75b7-181">Überprüfen Sie **DTC-Netzwerkzugriff** und **ausgehende zulassen**.</span><span class="sxs-lookup"><span data-stu-id="b75b7-181">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5. <span data-ttu-id="b75b7-182">Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.</span><span class="sxs-lookup"><span data-stu-id="b75b7-182">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="b75b7-183">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b75b7-183">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b75b7-184">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b75b7-184">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b75b7-185">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b75b7-185">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b75b7-186">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="b75b7-186">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b75b7-187">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b75b7-187">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
