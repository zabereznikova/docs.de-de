---
title: WS-Transaktionsfluss
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 8b037a2faa6ed5f7c77ea9347b92af7dc1ec2c27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183167"
---
# <a name="ws-transaction-flow"></a>WS-Transaktionsfluss
In diesem Beispiel werden die Verwendung einer clientkoordinierten Transaktion und die Client- und Serveroptionen für den Transaktionsfluss unter Verwendung des WS-Atomic-Transaktionsprotokolls oder des OleTransactions-Protokolls erläutert. Dieses Beispiel basiert auf dem [Ersten Schritte,](../../../../docs/framework/wcf/samples/getting-started-sample.md) der einen Rechnerdienst implementiert, `TransactionFlowAttribute` aber die Vorgänge werden zugeschrieben, um die Verwendung der mit der **TransactionFlowOption-Enumeration** zu demonstrieren, um zu bestimmen, in welchem Grad transaktionsfluss aktiviert ist. Innerhalb des Bereichs des Transaktionsflusses wird ein Protokoll der angeforderten Vorgänge in eine Datenbank geschrieben. Dieses bleibt dort erhalten, bis die clientkoordinierte Transaktion fertiggestellt wurde. Wenn die Clienttransaktion nicht fertiggestellt wird, stellt die Webdiensttransaktion sicher, dass die entsprechenden Aktualisierungen der Datenbank nicht ausgeführt werden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Nach der Initiierung einer Verbindung zu dem Dienst und einer Transaktion greift der Client auf mehrere Dienstvorgänge zu. Der Vertrag für den Dienst ist folgendermaßen definiert, dabei veranschaulicht jeder der Vorgänge eine andere Einstellung für die `TransactionFlowOption`.  

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

 Auf diese Weise werden die Vorgänge in der Reihenfolge, in der sie verarbeitet werden sollten, definiert:  
  
- Eine `Add`-Vorgangsanforderung muss einen Transaktionsfluss beinhalten.  
  
- Eine `Subtract`-Vorgangsanforderung kann einen Transaktionsfluss beinhalten.  
  
- Eine `Multiply`-Vorgangsanforderung darf keinen Transaktionsfluss durch die explizite NotAllowed-Einstellung beinhalten.  
  
- Eine `Divide`-Vorgangsanforderung darf keinen Transaktionsfluss durch die Auslassung eines `TransactionFlow`-Attributs beinhalten.  
  
 Um den Transaktionsfluss zu aktivieren, müssen bindungen mit der [ \<transactionFlow>](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) aktivierten Eigenschaft zusätzlich zu den entsprechenden Vorgangsattributen verwendet werden. In diesem Beispiel macht die Dienstkonfiguration zusätzlich zu einem Metadatenaustausch-Endpunkt einen TCP-Endpunkt und einen HTTP-Endpunkt verfügbar. Der TCP-Endpunkt und der HTTP-Endpunkt verwenden die folgenden Bindungen, die beide die [ \<transactionFlow->-Eigenschaft](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) aktiviert haben.  
  
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
> Die vom System bereitgestellte netTcpBinding ermöglicht die Festlegung des transactionProtocol, während die vom System bereitgestellte wsHttpBinding nur das interoperablere WSAtomicTransactionOctober2004-Protokoll verwendet. Das OleTransactions-Protokoll ist nur für Windows Communication Foundation (WCF)-Clients verfügbar.  
  
 Für die Klasse, die die `ICalculator`-Schnittstelle implementiert, werden alle Methoden mit auf <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> festgelegter `true`-Eigenschaft attributiert. Diese Einstellung deklariert, dass alle innerhalb der Methode ausgeführten Aktionen innerhalb des Bereichs einer Transaktion auftreten. In diesem Fall beinhalten die ausgeführten Aktionen auch Aufzeichnung in der Protokolldatenbank. Wenn die Vorgangsanforderung einen Transaktionsfluss beinhaltet, treten die Aktionen innerhalb des Bereichs der eingehenden Transaktion auf, oder es wird automatisch ein neuer Transaktionsbereich erstellt.  
  
> [!NOTE]
> Die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft definiert das Verhalten lokal in Bezug auf die Implementierungen der Dienstmethode und definiert nicht die Fähigkeit des Clients für oder die Anforderung eines Transaktionsflusses.  

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

 Auf dem Client werden die `TransactionFlowOption`-Einstellungen des Diensts für die Vorgänge in der generierten Definition des Clients für die `ICalculator`-Schnittstelle wiedergegeben. Außerdem werden die `transactionFlow`-Eigenschaftseinstellungen des Diensts in der Anwendungskonfiguration des Clients wiedergegeben. Der Client kann den Transport und das Protokoll auswählen, indem er den entsprechenden `endpointConfigurationName` auswählt.  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> Das beobachtete Verhalten dieses Beispiels ist das gleiche, unabhängig davon, welches Protokoll oder welcher Transport ausgewählt wird.  
  
 Nach der Initiierung der Verbindung zu dem Dienst erstellt der Client einen neuen `TransactionScope` um die Aufrufe der Dienstvorgänge.  

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

 Die Aufrufe der Vorgänge sehen folgendermaßen aus:  
  
- Die `Add`-Anforderung übergibt die erforderliche Transaktion an den Dienst, und die Aktionen des Diensts treten innerhalb des Bereichs der Transaktion des Clients auf.  
  
- Die erste `Subtract`-Anforderung übergibt die zulässige Transaktion ebenfalls an den Dienst, und die Aktionen des Diensts treten erneut innerhalb des Bereichs der Transaktion des Clients auf.  
  
- Die zweite `Subtract`-Anforderung wird innerhalb eines neuen Transaktionsbereichs ausgeführt, der mit der `TransactionScopeOption.Suppress`-Option deklariert wird. Auf diese Weise wird die initiale äußere Transaktion des Clients unterdrückt, und die Anforderung übergibt keine Transaktion an den Dienst. Mithilfe dieses Verfahrens kann ein Client explizit deaktiviert werden, und es wird verhindert, dass eine Transaktion an einen Dienst übergeben wird, wenn diese nicht erforderlich ist. Die Aktionen des Diensts treten innerhalb des Bereichs einer neuen und unverbundenen Transaktion auf.  
  
- Die `Multiply`-Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition der `ICalculator`-Schnittstelle ein <xref:System.ServiceModel.TransactionFlowAttribute> beinhaltet, für das <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed` festgelegt wurde.  
  
- Die `Divide`-Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition der `ICalculator`-Schnittstelle wiederum kein `TransactionFlowAttribute` beinhaltet. Die Aktionen des Diensts treten erneut innerhalb des Bereichs einer anderen neuen und unverbundenen Transaktion auf.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
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
  
 Die Protokollierung der Dienstvorgangsanforderungen wird im Konsolenfenster des Diensts angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 Nach einer erfolgreichen Ausführung wird der Transaktionsbereich des Clients abgeschlossen, und alle Aktionen innerhalb des Bereichs werden ausgeführt. Vor allem werden die erwähnten fünf Datensätze in der Datenbank des Diensts beibehalten. Die beiden ersten sind innerhalb des Bereichs der Transaktion des Clients aufgetreten.  
  
 Wenn im `TransactionScope` des Clients eine Ausnahme aufgetreten ist, kann die Transaktion nicht abgeschlossen werden. Dies führt dazu, dass die innerhalb des Bereichs protokollierten Datensätze nicht an die Datenbank übergeben werden. Dieser Effekt kann beobachtet werden, wenn das Beispiel erneut ausgeführt wird, nachdem der Aufruf zum Abschließen des äußeren `TransactionScope` auskommentiert wurde. Bei einer solchen Ausführung werden nur die letzen drei Aktionen protokolliert (die zweite `Subtract`-, die `Multiply`- und die `Divide`-Anforderung), da die Clienttransaktion nicht an diese übergeben wurde.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Befolgen Sie die Anweisungen unter Erstellen der Windows Communication [Foundation-Beispiele,](../../../../docs/framework/wcf/samples/building-the-samples.md) um die Version von .NET zu erstellen.  
  
2. Vergewissern Sie sich, dass SQL Server Express Edition oder SQL Server installiert ist. Stellen Sie außerdem sicher, dass die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei des Diensts ordnungsgemäß festgelegt ist. Wenn Sie das Beispiel ohne eine Datenbank ausführen möchten, legen Sie den `usingSql`-Wert in der Anwendungskonfigurationsdatei des Diensts auf `false` fest.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Aktivieren Sie bei einer computerübergreifenden Konfiguration Distributed Transaction Coordinator entsprechend den nachfolgenden Anweisungen, und aktivieren Sie mit dem Tool WsatConfig.exe aus dem Windows SDK die Netzwerkunterstützung von WCF-Transaktionen. Informationen zum Einrichten von WsatConfig.exe finden Sie unter [Konfigurieren des WS-Atomic Transaction Support](../feature-details/configuring-ws-atomic-transaction-support.md).  
  
 Unabhängig davon, ob Sie das Beispiel auf demselben Computer oder auf verschiedenen Computern ausführen, müssen Sie den Microsoft Distributed Transaction Coordinator (MSDTC) so konfigurieren, dass der Netzwerktransaktionsfluss aktiviert wird, und das Tool WsatConfig.exe verwenden, um die Netzwerkunterstützung für WCF-Transaktionen zu aktivieren.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>So konfigurieren Sie Microsoft Distributed Transaction Coordinator (MSDTC) zum Ausführen des Beispiels  
  
1. Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2003 oder Windows XP entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.  
  
    1. Navigieren Sie im **Startmenü** zur **Systemsteuerung**, dann zu **Administrative Tools**und dann zu **Component Services**.  
  
    2. Erweitern Sie **Component Services**. Öffnen Sie den Ordner **Computer.**  
  
    3. Klicken Sie mit der rechten Maustaste auf **"Computer",** und wählen Sie **Eigenschaften**aus.  
  
    4. Klicken Sie auf der Registerkarte **MSDTC** auf **Sicherheitskonfiguration**.  
  
    5. Überprüfen Sie **den Netzwerk-DTC-Zugriff,** und **lassen Sie eingehend zu.**  
  
    6. Klicken Sie auf **OK**, und klicken Sie dann auf **Ja,** um den MSDTC-Dienst neu zu starten.  
  
    7. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
2. Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2008 oder Windows Vista entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.  
  
    1. Navigieren Sie im **Startmenü** zur **Systemsteuerung**, dann zu **Administrative Tools**und dann zu **Component Services**.  
  
    2. Erweitern Sie **Component Services**. Öffnen Sie den Ordner **Computer.** Wählen Sie **Distributed Transaction Coordinator**aus.  
  
    3. Klicken Sie mit der rechten Maustaste auf **DTC-Koordinator,** und wählen Sie **Eigenschaften**aus.  
  
    4. Überprüfen Sie auf der Registerkarte **Sicherheit** den **Netzwerk-DTC-Zugriff,** und **lassen Sie eingehend zu.**  
  
    5. Klicken Sie auf **OK**, und klicken Sie dann auf **Ja,** um den MSDTC-Dienst neu zu starten.  
  
    6. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
3. Konfigurieren Sie auf dem Clientcomputer MSDTC zum Zulassen von ausgehenden Netzwerktransaktionen:  
  
    1. Navigieren Sie im **Startmenü** zu , dann zu **Administrative Tools**und dann zu `Control Panel` **Component Services**.  
  
    2. Klicken Sie mit der rechten Maustaste auf **"Computer",** und wählen Sie **Eigenschaften**aus.  
  
    3. Klicken Sie auf der Registerkarte **MSDTC** auf **Sicherheitskonfiguration**.  
  
    4. Überprüfen Sie **den Netzwerk-DTC-Zugriff,** und **lassen Sie ausgehende**.  
  
    5. Klicken Sie auf **OK**, und klicken Sie dann auf **Ja,** um den MSDTC-Dienst neu zu starten.  
  
    6. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
