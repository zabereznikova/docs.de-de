---
title: WS-Transaktionsfluss
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 35af3090c0f898578a5f8dfb81d02d22a0074ad2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264856"
---
# <a name="ws-transaction-flow"></a>WS-Transaktionsfluss
In diesem Beispiel werden die Verwendung einer clientkoordinierten Transaktion und die Client- und Serveroptionen für den Transaktionsfluss unter Verwendung des WS-AtomicTransaction-Protokolls oder des OleTransactions-Protokolls erläutert. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert, aber die Vorgänge zum Veranschaulichen der Verwendung von attributiert sind die `TransactionFlowAttribute` mit der **TransactionFlowOption** Enumeration, um zu bestimmen, in welchem Umfang der Transaktionsfluss aktiviert ist. Innerhalb des Bereichs des Transaktionsflusses wird ein Protokoll der angeforderten Vorgänge in eine Datenbank geschrieben. Dieses bleibt dort erhalten, bis die clientkoordinierte Transaktion fertiggestellt wurde. Wenn die Clienttransaktion nicht fertiggestellt wird, stellt die Webdiensttransaktion sicher, dass die entsprechenden Aktualisierungen der Datenbank nicht ausgeführt werden.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
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
  
-   Eine `Add`-Vorgangsanforderung muss einen Transaktionsfluss beinhalten.  
  
-   Eine `Subtract`-Vorgangsanforderung kann einen Transaktionsfluss beinhalten.  
  
-   Eine `Multiply`-Vorgangsanforderung darf keinen Transaktionsfluss durch die explizite NotAllowed-Einstellung beinhalten.  
  
-   Eine `Divide`-Vorgangsanforderung darf keinen Transaktionsfluss durch die Auslassung eines `TransactionFlow`-Attributs beinhalten.  
  
 Zum Aktivieren des Transaktionsflusses, Bindungen, bei denen die [ \<TransactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) -Eigenschaft aktiviert ist, muss zusätzlich zu den entsprechenden Vorgangsattributen verwendet werden. In diesem Beispiel macht die Dienstkonfiguration zusätzlich zu einem Metadatenaustausch-Endpunkt einen TCP-Endpunkt und einen HTTP-Endpunkt verfügbar. Der TCP-Endpunkt und den HTTP-Endpunkt verwenden Sie die folgenden Bindungen, die jeweils die [ \<TransactionFlow >](../../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) -Eigenschaft aktiviert ist.  
  
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
>  Die vom System bereitgestellte netTcpBinding ermöglicht die Festlegung des transactionProtocol, während die vom System bereitgestellte wsHttpBinding nur das interoperablere WSAtomicTransactionOctober2004-Protokoll verwendet. Die OleTransactions, die Protokoll nur zur Verfügung steht, verwenden von Windows Communication Foundation (WCF)-Clients.  
  
 Für die Klasse, die die `ICalculator`-Schnittstelle implementiert, werden alle Methoden mit auf <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> festgelegter `true`-Eigenschaft attributiert. Diese Einstellung deklariert, dass alle innerhalb der Methode ausgeführten Aktionen innerhalb des Bereichs einer Transaktion auftreten. In diesem Fall beinhalten die ausgeführten Aktionen auch Aufzeichnung in der Protokolldatenbank. Wenn die Vorgangsanforderung einen Transaktionsfluss beinhaltet, treten die Aktionen innerhalb des Bereichs der eingehenden Transaktion auf, oder es wird automatisch ein neuer Transaktionsbereich erstellt.  
  
> [!NOTE]
>  Die <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>-Eigenschaft definiert das Verhalten lokal in Bezug auf die Implementierungen der Dienstmethode und definiert nicht die Fähigkeit des Clients für oder die Notwendigkeit eines Transaktionsflusses.  

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
>  Das beobachtete Verhalten dieses Beispiels ist das gleiche, unabhängig davon, welches Protokoll oder welcher Transport ausgewählt wird.  
  
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
  
-   Die `Add`-Anforderung übergibt die erforderliche Transaktion an den Dienst, und die Aktionen des Diensts treten innerhalb des Bereichs der Transaktion des Clients auf.  
  
-   Die erste `Subtract`-Anforderung übergibt die zulässige Transaktion ebenfalls an den Dienst, und die Aktionen des Diensts treten erneut innerhalb des Bereichs der Transaktion des Clients auf.  
  
-   Die zweite `Subtract`-Anforderung wird innerhalb eines neuen Transaktionsbereichs ausgeführt, der mit der `TransactionScopeOption.Suppress`-Option deklariert wird. Auf diese Weise wird die initiale äußere Transaktion des Clients unterdrückt, und die Anforderung übergibt keine Transaktion an den Dienst. Mithilfe dieses Verfahrens kann ein Client explizit deaktiviert werden, und es wird verhindert, dass eine Transaktion an einen Dienst übergeben wird, wenn diese nicht erforderlich ist. Die Aktionen des Diensts treten innerhalb des Bereichs einer neuen und unverbundenen Transaktion auf.  
  
-   Die `Multiply` -Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition von der die `ICalculator` Schnittstelle enthält eine <xref:System.ServiceModel.TransactionFlowAttribute> festgelegt <xref:System.ServiceModel.TransactionFlowOption> `NotAllowed`.  
  
-   Die `Divide`-Anforderung übergibt keine Transaktion an den Dienst, da die generierte Definition der `ICalculator`-Schnittstelle wiederum kein `TransactionFlowAttribute` beinhaltet. Die Aktionen des Diensts treten erneut innerhalb des Bereichs einer anderen neuen und unverbundenen Transaktion auf.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
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
  
 Die Protokollierung der Dienstvorgangsanforderungen wird im Konsolenfenster des Diensts angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
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
  
1.  Um die C#- oder Visual Basic .NET Version der Lösung zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
2.  Vergewissern Sie sich, dass SQL Server Express Edition oder SQL Server installiert ist. Stellen Sie außerdem sicher, dass die Verbindungszeichenfolge in der Anwendungskonfigurationsdatei des Diensts ordnungsgemäß festgelegt ist. Wenn Sie das Beispiel ohne eine Datenbank ausführen möchten, legen Sie den `usingSql`-Wert in der Anwendungskonfigurationsdatei des Diensts auf `false` fest.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Aktivieren Sie bei einer computerübergreifenden Konfiguration Distributed Transaction Coordinator entsprechend den nachfolgenden Anweisungen, und aktivieren Sie mit dem Tool WsatConfig.exe aus dem Windows SDK die Netzwerkunterstützung von WCF-Transaktionen. Finden Sie unter [WS-AtomicTransaction-Unterstützung konfigurieren](https://go.microsoft.com/fwlink/?LinkId=190370) Informationen zum Einrichten von WsatConfig.exe festlegen.  
  
 Ob Sie das Beispiel auf demselben Computer oder auf anderen Computern ausführen, müssen Sie der Microsoft Distributed Transaction Coordinator (MSDTC) zum Aktivieren der Netzwerk-Transaktionsfluss und verwenden das Tool WsatConfig.exe die Netzwerkunterstützung von WCF-Transaktionen aktivieren konfigurieren.  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a>So konfigurieren Sie Microsoft Distributed Transaction Coordinator (MSDTC) zum Ausführen des Beispiels  
  
1.  Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2003 oder Windows XP entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.  
  
    1.  Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.  
  
    2.  Erweitern Sie **Komponentendienste**. Öffnen der **Computer** Ordner.  
  
    3.  Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.  
  
    4.  Auf der **MSDTC** auf **Sicherheitskonfiguration**.  
  
    5.  Überprüfen Sie **DTC-Netzwerkzugriff** und **zulassen eingehender**.  
  
    6.  Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.  
  
    7.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
2.  Konfigurieren Sie MSDTC auf einem Dienstcomputer unter Windows Server 2008 oder Windows Vista entsprechend den folgenden Anweisungen so, dass eingehende Netzwerktransaktionen zugelassen werden.  
  
    1.  Von der **starten** Menü navigieren Sie zu **Systemsteuerung**, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.  
  
    2.  Erweitern Sie **Komponentendienste**. Öffnen der **Computer** Ordner. Wählen Sie **Distributed Transaction Coordinator**.  
  
    3.  Mit der rechten Maustaste **Distributed Transaction Coordinator** , und wählen Sie **Eigenschaften**.  
  
    4.  Auf der **Sicherheit** Registerkarte **DTC-Netzwerkzugriff** und **Allow Inbound**.  
  
    5.  Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.  
  
    6.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
3.  Konfigurieren Sie auf dem Clientcomputer MSDTC zum Zulassen von ausgehenden Netzwerktransaktionen:  
  
    1.  Von der **starten** Menü navigieren Sie zu `Control Panel`, klicken Sie dann **Verwaltung**, und klicken Sie dann **Komponentendienste**.  
  
    2.  Mit der rechten Maustaste **Arbeitsplatz** , und wählen Sie **Eigenschaften**.  
  
    3.  Auf der **MSDTC** auf **Sicherheitskonfiguration**.  
  
    4.  Überprüfen Sie **DTC-Netzwerkzugriff** und **ausgehende zulassen**.  
  
    5.  Klicken Sie auf **OK**, klicken Sie dann auf **Ja** den MSDTC-Dienst neu starten.  
  
    6.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
