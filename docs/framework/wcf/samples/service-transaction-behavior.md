---
title: Diensttransaktionsverhalten
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: bfdf0c9ddb8654bf7a6736bcccb0d9350e9a12a6
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50042492"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="51e92-102">Diensttransaktionsverhalten</span><span class="sxs-lookup"><span data-stu-id="51e92-102">Service Transaction Behavior</span></span>
<span data-ttu-id="51e92-103">In diesem Beispiel werden die Verwendung einer clientkoordinierten Transaktion und die Einstellungen von ServiceBehaviorAttribute und OperationBehaviorAttribute zum Steuern des Diensttransaktionsverhaltens veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="51e92-103">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="51e92-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert, aber wird erweitert, um ein Serverprotokoll der ausgeführten Vorgänge in einer Datenbanktabelle und eine statusbehaftete laufende Summe der rechnervorgänge zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="51e92-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="51e92-105">Beibehaltene Schreibvorgänge in der Serverprotokolltabelle sind abhängig vom Ergebnis einer clientkoordinierten Transaktion. Wenn die Clienttransaktion nicht abgeschlossen wird, stellt die Webdiensttransaktion sicher, dass die Aktualisierungen der Datenbank nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51e92-105">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e92-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="51e92-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="51e92-107">Der Vertrag für den Dienst definiert, dass für alle Vorgänge eine Transaktion mit Anforderungen übergeben werden muss:</span><span class="sxs-lookup"><span data-stu-id="51e92-107">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",  
                    SessionMode = SessionMode.Required)]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Subtract(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Multiply(double n);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Divide(double n);  
}  
```  
  
 <span data-ttu-id="51e92-108">Zum Aktivieren des eingehenden Transaktionsflusses wird der Dienst mit der vom System bereitgestellten wsHttpBinding konfiguriert, wobei das transactionFlow-Attribut auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="51e92-108">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="51e92-109">Diese Bindung verwendet das interoperable WSAtomicTransactionOctober2004-Protokoll:</span><span class="sxs-lookup"><span data-stu-id="51e92-109">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="transactionalBinding" transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="51e92-110">Nach dem Initiieren einer Verbindung mit dem Dienst und einer Transaktion greift der Client auf mehrere Dienstvorgänge im Bereich der Transaktion zu, schließt die Transaktion ab und trennt die Verbindung:</span><span class="sxs-lookup"><span data-stu-id="51e92-110">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>  
  
```csharp
// Create a client  
CalculatorClient client = new CalculatorClient();  
  
// Create a transaction scope with the default isolation level of Serializable  
using (TransactionScope tx = new TransactionScope())  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation.  
    double value = 100.00D;  
    Console.WriteLine("  Adding {0}, running total={1}",  
                                        value, client.Add(value));  
  
    // Call the Subtract service operation.  
    value = 45.00D;  
    Console.WriteLine("  Subtracting {0}, running total={1}",  
                                        value, client.Subtract(value));  
  
    // Call the Multiply service operation.  
    value = 9.00D;  
    Console.WriteLine("  Multiplying by {0}, running total={1}",  
                                        value, client.Multiply(value));  
  
    // Call the Divide service operation.  
    value = 15.00D;  
    Console.WriteLine("  Dividing by {0}, running total={1}",  
                                        value, client.Divide(value));  
  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
  
// Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
 <span data-ttu-id="51e92-111">Bei dem Dienst gibt es drei Attribute, die Auswirkungen auf das Diensttransaktionsverhalten haben. Dies geschieht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="51e92-111">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>  
  
-   <span data-ttu-id="51e92-112">Für `ServiceBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="51e92-112">On the `ServiceBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="51e92-113">Die `TransactionTimeout`-Eigenschaft gibt den Zeitraum an, innerhalb dessen eine Transaktion abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="51e92-113">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="51e92-114">In diesem Beispiel ist sie auf 30 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="51e92-114">In this sample it is set to 30 seconds.</span></span>  
  
    -   <span data-ttu-id="51e92-115">Die `TransactionIsolationLevel`-Eigenschaft gibt die Isolationsstufe an, die der Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51e92-115">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="51e92-116">Dies ist zur Übereinstimmung mit der Isolationsstufe des Clients erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51e92-116">This is required to match the client's isolation level.</span></span>  
  
    -   <span data-ttu-id="51e92-117">Die `ReleaseServiceInstanceOnTransactionComplete`-Eigenschaft legt fest, ob die Dienstinstanz beim Abschluss einer Transaktion wiederverwendet wird.</span><span class="sxs-lookup"><span data-stu-id="51e92-117">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="51e92-118">Durch das Festlegen auf `false` behält der Dienst die gleiche Dienstinstanz über die Vorgangsanforderungen hinweg bei.</span><span class="sxs-lookup"><span data-stu-id="51e92-118">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="51e92-119">Dies ist für das Beibehalten der laufenden Gesamtsumme erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51e92-119">This is required to maintain the running total.</span></span> <span data-ttu-id="51e92-120">Beim Festlegen auf `true` wird nach jeder abgeschlossenen Aktion eine neue Instanz generiert.</span><span class="sxs-lookup"><span data-stu-id="51e92-120">If set to `true`, a new instance is generated after each completed action.</span></span>  
  
    -   <span data-ttu-id="51e92-121">Die `TransactionAutoCompleteOnSessionClose`-Eigenschaft gibt an, ob ausstehende Transaktionen abgeschlossen werden, wenn die Sitzung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="51e92-121">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="51e92-122">Durch Festlegung auf `false`, die einzelnen Vorgänge sind erforderlich, um entweder die `OperationBehaviorAttribute``TransactionAutoComplete` Eigenschaft, um `true` oder explizit einen Aufruf von erfordern die `SetTransactionComplete` Methode, um Transaktionen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-122">By setting it to `false`, the individual operations are required to either set the `OperationBehaviorAttribute``TransactionAutoComplete` property to `true` or to explicitly require a call to the `SetTransactionComplete` method to complete transactions.</span></span> <span data-ttu-id="51e92-123">In diesem Beispiel werden beide Ansätze veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="51e92-123">This sample demonstrates both approaches.</span></span>  
  
-   <span data-ttu-id="51e92-124">Für `ServiceContractAttribute`:</span><span class="sxs-lookup"><span data-stu-id="51e92-124">On the `ServiceContractAttribute`:</span></span>  
  
    -   <span data-ttu-id="51e92-125">Die `SessionMode`-Eigenschaft gibt an, ob der Dienst die entsprechenden Anforderungen in eine logische Sitzung korreliert.</span><span class="sxs-lookup"><span data-stu-id="51e92-125">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="51e92-126">Da dieser Dienst Vorgänge umfasst, bei denen die OperationBehaviorAttribute TransactionAutoComplete-Eigenschaft auf `false` festgelegt ist (Multiply und Divide), muss `SessionMode.Required` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="51e92-126">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="51e92-127">Der Multiply-Vorgang schließt seine Transaktion beispielsweise nicht ab und benötigt stattdessen den Abschluss eines späteren Aufrufs von Divide mithilfe der `SetTransactionComplete`-Methode. Der Dienst muss bestimmen können, dass diese Vorgänge in der gleichen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51e92-127">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>  
  
-   <span data-ttu-id="51e92-128">Für `OperationBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="51e92-128">On the `OperationBehaviorAttribute`:</span></span>  
  
    -   <span data-ttu-id="51e92-129">Die `TransactionScopeRequired`-Eigenschaft gibt an, ob die Aktionen des Vorgangs innerhalb eines Transaktionsbereichs ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="51e92-129">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="51e92-130">Dies ist für alle Vorgänge in diesem Beispiel auf `true` festgelegt, und da der Client seine Transaktion auf alle Vorgänge überträgt, treten die Aktionen im Bereich dieser Clienttransaktion auf.</span><span class="sxs-lookup"><span data-stu-id="51e92-130">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>  
  
    -   <span data-ttu-id="51e92-131">Die `TransactionAutoComplete`-Eigenschaft legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine nicht behandelten Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="51e92-131">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="51e92-132">Wie oben beschrieben, ist dies für den Add-Vorgang und den Subtract-Vorgang auf `true` festgelegt, für den Multiply-Vorgang und den Divide-Vorgang jedoch auf `false`.</span><span class="sxs-lookup"><span data-stu-id="51e92-132">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="51e92-133">Der Add-Vorgang und der Subtract-Vorgang schließen die Aktionen automatisch ab, der Divide-Vorgang schließt seine Aktionen durch einen expliziten Aufruf der `SetTransactionComplete`-Methode ab, und der Multiply-Vorgang schließt die Aktionen nicht ab, sondern benötigt einen späteren Aufruf, beispielsweise von Divide, zum Abschließen der Aktionen.</span><span class="sxs-lookup"><span data-stu-id="51e92-133">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>  
  
 <span data-ttu-id="51e92-134">Die attributierte Dienstimplementierung lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="51e92-134">The attributed service implementation is as follows:</span></span>  
  
```csharp
[ServiceBehavior(  
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
    TransactionTimeout = "00:00:30",  
    ReleaseServiceInstanceOnTransactionComplete = false,  
    TransactionAutoCompleteOnSessionClose = false)]  
public class CalculatorService : ICalculator  
{  
    double runningTotal;  
  
    public CalculatorService()  
    {  
        Console.WriteLine("Creating new service instance...");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Add(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));  
        runningTotal = runningTotal + n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public double Subtract(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));  
        runningTotal = runningTotal - n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Multiply(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal * n;  
        return runningTotal;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]  
    public double Divide(double n)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));  
        runningTotal = runningTotal / n;  
        OperationContext.Current.SetTransactionComplete();  
        return runningTotal;  
    }  
  
    // Logging method ommitted for brevity  
}   
```  
  
 <span data-ttu-id="51e92-135">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51e92-135">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="51e92-136">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-136">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Starting transaction  
Performing calculations...  
  Adding 100, running total=100  
  Subtracting 45, running total=55  
  Multiplying by 9, running total=495  
  Dividing by 15, running total=33  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="51e92-137">Die Protokollierung der Dienstvorgangsanforderungen wird im Konsolenfenster des Diensts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51e92-137">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="51e92-138">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-138">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Press <ENTER> to terminate service.  
Creating new service instance...  
  Writing row 1 to database: Adding 100 to 0  
  Writing row 2 to database: Subtracting 45 from 100  
  Writing row 3 to database: Multiplying 55 by 9  
  Writing row 4 to database: Dividing 495 by 15  
```  
  
 <span data-ttu-id="51e92-139">Zusätzlich zur laufenden Summe der Berechnungen erstellt der Dienst einen Bericht über die Instanzenerstellung (eine Instanz zu diesem Beispiel) und protokolliert die Vorgangsanforderungen in einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="51e92-139">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="51e92-140">Da alle Anforderung die Transaktion des Clients übergeben, führt ein Fehler beim Abschließen dieser Transaktion zu einem Rollback aller Datenbankvorgänge.</span><span class="sxs-lookup"><span data-stu-id="51e92-140">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="51e92-141">Dies kann auf mehrere Arten veranschaulicht werden:</span><span class="sxs-lookup"><span data-stu-id="51e92-141">This can be demonstrated in a number of ways:</span></span>  
  
-   <span data-ttu-id="51e92-142">Kommentieren Sie den Aufruf von `tx.Complete`() durch den Client aus, und führen Sie das Beispiel erneut aus. So verlässt der Client den Transaktionsbereich, ohne die Transaktion abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-142">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>  
  
-   <span data-ttu-id="51e92-143">Kommentieren Sie den Aufruf des Divide-Dienstvorgangs aus. Dies führt dazu, dass die vom Multiply-Vorgang initiierte Aktion nicht abgeschlossen werden kann. Die Transaktion des Clients kann somit auch nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="51e92-143">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>  
  
-   <span data-ttu-id="51e92-144">Lösen Sie an einer beliebigen Stelle im Transaktionsbereich des Clients eine nicht behandelte Ausnahme aus. Diese führt ebenfalls dazu, dass der Client die Transaktion nicht abschließen kann.</span><span class="sxs-lookup"><span data-stu-id="51e92-144">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>  
  
 <span data-ttu-id="51e92-145">Alle diese Aktionen führen dazu, dass die in diesem Bereich ausgeführten Vorgänge beendet werden und dass die Anzahl der in der Datenbank beibehaltenen Zeilen nicht inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="51e92-145">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e92-146">Während des Buildprozesses wird die Datenbankdatei in den bin-Ordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="51e92-146">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="51e92-147">Sie müssen diese Kopie der Datenbankdatei betrachten, um die im Protokoll gespeicherten Zeilen zu ermitteln, und nicht die Datei im Visual Studio-Projekt.</span><span class="sxs-lookup"><span data-stu-id="51e92-147">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="51e92-148">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="51e92-148">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="51e92-149">Stellen Sie sicher, dass SQL Server 2005 Express Edition oder SQL Server 2005 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="51e92-149">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="51e92-150">In der Datei App.config des Diensts ist `connectionString` für die Datenbank möglicherweise festgelegt oder die Datenbankinteraktionen sind deaktiviert, indem der `usingSql`-Wert für appSettings auf `false` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="51e92-150">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>  
  
2.  <span data-ttu-id="51e92-151">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="51e92-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="51e92-152">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51e92-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
 <span data-ttu-id="51e92-153">Wenn Sie das Beispiel computerübergreifend ausführen, müssen Sie konfigurieren den Microsoft Distributed Transaction Coordinator (MSDTC) zum Aktivieren der Netzwerk-Transaktionsfluss und verwenden das Tool WsatConfig.exe zum Netzwerk der Windows Communication Foundation (WCF)-Transaktionen aktivieren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51e92-153">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="51e92-154">So konfigurieren Sie Microsoft Distributed Transaction Coordinator (MSDTC) zum Ausführen des Beispiels computerübergreifend</span><span class="sxs-lookup"><span data-stu-id="51e92-154">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>  
  
1.  <span data-ttu-id="51e92-155">Konfigurieren Sie auf dem Dienstcomputer MSDTC zum Zulassen von eingehenden Netzwerktransaktionen.</span><span class="sxs-lookup"><span data-stu-id="51e92-155">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>  
  
    1.  <span data-ttu-id="51e92-156">Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="51e92-156">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="51e92-157">Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51e92-157">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="51e92-158">Auf der **MSDTC** auf **Sicherheitskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51e92-158">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="51e92-159">Überprüfen Sie **DTC-Netzwerkzugriff** und **zulassen eingehender**.</span><span class="sxs-lookup"><span data-stu-id="51e92-159">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5.  <span data-ttu-id="51e92-160">Klicken Sie auf **Ja** den MS DTC-Dienst neu starten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="51e92-160">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="51e92-161">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-161">Click **OK** to close the dialog box.</span></span>  
  
2.  <span data-ttu-id="51e92-162">Konfigurieren Sie auf dem Dienstcomputer und auf dem Clientcomputer die Windows-Firewall so, dass Microsoft Distributed Transaction Coordinator (MSDTC) in der Liste der ausgeschlossenen Anwendungen angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="51e92-162">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>  
  
    1.  <span data-ttu-id="51e92-163">Führen Sie die Windows-Firewall-Anwendung über die Systemsteuerung aus.</span><span class="sxs-lookup"><span data-stu-id="51e92-163">Run the Windows Firewall application from Control Panel.</span></span>  
  
    2.  <span data-ttu-id="51e92-164">Von der **Ausnahmen** auf **Programm hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="51e92-164">From the **Exceptions** tab, click **Add Program**.</span></span>  
  
    3.  <span data-ttu-id="51e92-165">Navigieren Sie zum Ordner C:\WINDOWS\System32.</span><span class="sxs-lookup"><span data-stu-id="51e92-165">Browse to the folder C:\WINDOWS\System32.</span></span>  
  
    4.  <span data-ttu-id="51e92-166">Wählen Sie Msdtc.exe aus, und klicken Sie auf **öffnen**.</span><span class="sxs-lookup"><span data-stu-id="51e92-166">Select Msdtc.exe and click **Open**.</span></span>  
  
    5.  <span data-ttu-id="51e92-167">Klicken Sie auf **OK** schließen die **Programm hinzufügen** (Dialogfeld), und klicken Sie auf **OK** erneut aus, um das Windows-Firewall-Applet zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-167">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>  
  
3.  <span data-ttu-id="51e92-168">Konfigurieren Sie auf dem Clientcomputer MSDTC zum Zulassen von ausgehenden Netzwerktransaktionen:</span><span class="sxs-lookup"><span data-stu-id="51e92-168">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1.  <span data-ttu-id="51e92-169">Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="51e92-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2.  <span data-ttu-id="51e92-170">Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51e92-170">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3.  <span data-ttu-id="51e92-171">Auf der **MSDTC** auf **Sicherheitskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="51e92-171">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4.  <span data-ttu-id="51e92-172">Überprüfen Sie **DTC-Netzwerkzugriff** und **ausgehende zulassen**.</span><span class="sxs-lookup"><span data-stu-id="51e92-172">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5.  <span data-ttu-id="51e92-173">Klicken Sie auf **Ja** den MS DTC-Dienst neu starten, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="51e92-173">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="51e92-174">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51e92-174">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51e92-175">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="51e92-175">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51e92-176">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="51e92-176">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="51e92-177">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="51e92-177">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51e92-178">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="51e92-178">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`  
  
## <a name="see-also"></a><span data-ttu-id="51e92-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51e92-179">See Also</span></span>
