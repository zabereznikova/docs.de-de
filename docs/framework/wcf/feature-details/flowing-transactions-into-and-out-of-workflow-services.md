---
title: Transaktionsfluss in Workflowdienste und aus Workflowdiensten
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: ea14bc651258684fd31940aa6b88f9731348dcd1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978283"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Transaktionsfluss in Workflowdienste und aus Workflowdiensten
Workflowdienste und Clients können an Transaktionen teilnehmen.  Damit ein Dienstvorgang Teil einer Ambient-Transaktion wird, fügen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität in eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität ein. Alle Aufrufe, die von einer <xref:System.ServiceModel.Activities.Send>-Aktivität oder einer <xref:System.ServiceModel.Activities.SendReply>-Aktivität in <xref:System.ServiceModel.Activities.TransactedReceiveScope> durchgeführt werden, werden auch in der Ambient-Transaktion durchgeführt. Eine Workflowclientanwendung kann mit der <xref:System.Activities.Statements.TransactionScope>-Aktivität eine Ambient-Transaktion erstellen und Dienstvorgänge mithilfe der Ambient-Transaktion aufrufen. In diesem Thema wird die Erstellung eines Workflowdiensts und Workflowclients, die an Transaktionen teilnehmen, erläutert.  
  
> [!WARNING]
> Wenn eine Workflow Dienst Instanz innerhalb einer Transaktion geladen wird und der Workflow eine <xref:System.Activities.Statements.Persist> Aktivität enthält, wird die Workflow Instanz bis zum Timeout der Transaktion blockiert.  
  
> [!IMPORTANT]
> Es wird empfohlen, bei Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> alle empfangenen Nachrichten im Workflow in <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivitäten zu platzieren.  
  
> [!IMPORTANT]
> Wenn Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwenden und Nachrichten in der falschen Reihenfolge eintreffen, wird beim Versuch, die erste der Nachrichten außerhalb der normalen Reihenfolge zu übermitteln, der Workflow abgebrochen. Sie müssen sicherstellen, dass der Workflow im Leerlauf stets einen konsistenten Haltepunkt aufweist. Falls der Workflow abgebrochen wird, können Sie ihn auf diese Weise anhand eines früheren Persistenzpunkts erneut starten.  
  
### <a name="create-a-shared-library"></a>Erstellen einer freigegebenen Bibliothek  
  
1. Erstellen Sie eine neue leere Visual Studio-Projektmappe.  
  
2. Fügen Sie ein neues Klassenbibliotheksprojekt mit dem Namen `Common` hinzu. Fügen Sie Verweise auf die folgenden Assemblys hinzu:  
  
    - System.Activities.dll  
  
    - System.ServiceModel.dll  
  
    - System.ServiceModel.Activities.dll  
  
    - System.Transactions.dll  
  
3. Fügen Sie dem `PrintTransactionInfo`-Projekt eine neue Klasse mit dem Namen `Common` hinzu. Diese Klasse wird von <xref:System.Activities.NativeActivity> abgeleitet und überlädt die <xref:System.Activities.NativeActivity.Execute%2A>-Methode.  
  
    ```csharp
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     Diese native Aktivität, in der Informationen zur Ambient-Transaktion angezeigt werden, wird in den in diesem Thema verwendeten Dienst- und Clientworkflows eingesetzt. Erstellen Sie die Projekt Mappe, um diese Aktivität im **allgemeinen** Abschnitt der **Toolbox**verfügbar zu machen.  
  
### <a name="implement-the-workflow-service"></a>Implementieren des Workflowdiensts  
  
1. Fügen Sie dem `Common` Projekt einen neuen WCF-Workflow Dienst namens "`WorkflowService`" hinzu. Klicken Sie dazu mit der rechten Maustaste auf das Projekt `Common`, wählen Sie **Hinzufügen**, **Neues Element**aus, wählen Sie unter **installierte Vorlagen** die Option **Workflow** , und wählen Sie **WCF-Workflow Dienst**aus.  
  
     ![Hinzufügen eines Workflowdiensts](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. Löschen Sie die `ReceiveRequest`-Standardaktivität und `SendResponse`-Standardaktivität.  
  
3. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität in die `Sequential Service`-Aktivität. Legen Sie die Texteigenschaft auf `"Workflow Service starting ..."` fest, wie im folgenden Beispiel gezeigt.  
  
     ! [Hinzufügen einer "Write teline"-Aktivität zur Aktivität "sequenzieller Dienst" (./Media/Flowing-Transactions-into-and-out-of-Workflow-Services/Add-WriteLine-Sequential-Service.jpg)  
  
4. Verschieben Sie eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität. Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität befindet sich im Abschnitt **Messaging** der **Toolbox**. Die <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität besteht aus zwei Abschnitten: **Anforderung** und **Text**. Der **Anforderungs** Abschnitt enthält die <xref:System.ServiceModel.Activities.Receive> Aktivität. Der **Text** Abschnitt enthält die Aktivitäten, die innerhalb einer Transaktion ausgeführt werden sollen, nachdem eine Nachricht empfangen wurde.  
  
     ![Hinzufügen einer TransactedReceiveScope-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. Wählen Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität aus, und klicken Sie auf die Schaltfläche **Variablen** . Fügen Sie die folgenden Variablen hinzu:  
  
     ![Hinzufügen von Variablen zu transactedreceivescope](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > Sie können die standardmäßig vorhandene Datenvariable löschen. Sie können auch die vorhandene Handlevariable verwenden.  
  
6. Ziehen Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität per Drag & Drop im **Anforderungs** Abschnitt der Aktivität <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Legen Sie die folgenden Eigenschaften fest:  
  
    |property|Wert|  
    |--------------|-----------|  
    |CanCreateInstance|Wahr (aktivieren Sie das Kontrollkästchen)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Der Workflow müsste wie folgt aussehen:  
  
     ![Hinzufügen einer Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. Klicken Sie in der <xref:System.ServiceModel.Activities.Receive> Aktivität auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest:  
  
     ![Festlegen von Meldungs Einstellungen für die Receive-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Textabschnitt vom <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Verschieben Sie innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität zwei <xref:System.Activities.Statements.WriteLine>-Aktivitäten per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaften wie in der folgenden Tabelle gezeigt fest.  
  
    |Aktivität|Wert|  
    |--------------|-----------|  
    |1\. WriteLine|"Dienst: empfangen abgeschlossen"|  
    |2\. WriteLine|"Service: Received = " + requestMessage|  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Sequenz nach dem Hinzufügen von Write-in-Aktivitäten](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. Ziehen Sie die `PrintTransactionInfo` Aktivität nach der zweiten <xref:System.Activities.Statements.WriteLine> Aktivität im **Text** in der <xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivität, und legen Sie Sie dort ab.  
  
     ![Nach dem Hinzufügen von printtransaktioninfo Sequenzieren](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. Ziehen Sie eine <xref:System.Activities.Statements.Assign>-Aktivität per Drag &amp; Drop an die Stelle nach der `PrintTransactionInfo`-Aktivität, und legen Sie die Eigenschaften entsprechend der folgenden Tabelle fest.  
  
    |property|Wert|  
    |--------------|-----------|  
    |Beschreibung|replyMessage|  
    |Wert|"Service: Sending reply."|  
  
11. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf „Service: Begin reply“ fest.  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Nach dem Hinzufügen von Assign und WriteLine](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> Aktivität, und wählen Sie **SendReply erstellen** aus, und fügen Sie Sie nach dem letzten <xref:System.Activities.Statements.WriteLine> Klicken Sie in der `SendReplyToReceive` Aktivität auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest.  
  
     ![Einstellungen der Antwortmeldung](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. Ziehen Sie nach der `SendReplyToReceive` <xref:System.Activities.Statements.WriteLine.Text%2A>-Aktivität eine <xref:System.Activities.Statements.WriteLine> Aktivität, und legen Sie Sie auf "Service: Reply sent" fest.  
  
14. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an das Ende des Workflows, und legen Sie die Eigenschaft <xref:System.Activities.Statements.WriteLine.Text%2A> auf "Service: Workflow ends, press ENTER to exit" fest.  
  
     Der abgeschlossene Dienstworkflow müsste wie folgt aussehen:  
  
     ![Vollständiger Serviceworkflow](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a>Implementieren des Workflowclients  
  
1. Fügen Sie eine neue WCF-Workflowanwendung mit dem Namen `WorkflowClient` zum `Common`-Projekt hinzu. Klicken Sie dazu mit der rechten Maustaste auf das Projekt `Common`, wählen Sie **Hinzufügen**, **Neues Element...** , wählen Sie unter **installierte Vorlagen** die Option **Workflow** und dann **Aktivität**aus.  
  
     ![Aktivitätsprojekt hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop auf die Entwurfsoberfläche.  
  
3. Verschieben Sie in der <xref:System.Activities.Statements.Sequence>-Aktivität eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf `"Client: Workflow starting"` fest. Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Eine WriteLine-Aktivität hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. Verschieben Sie eine <xref:System.Activities.Statements.TransactionScope>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.  Wählen Sie die <xref:System.Activities.Statements.TransactionScope>-Aktivität aus, klicken Sie auf die Schaltfläche Variablen, und fügen Sie die folgenden Variablen hinzu.  
  
     ![Variablen zu TransactionScope hinzufügen](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität per Drag &amp; Drop in den Text der <xref:System.Activities.Statements.TransactionScope>-Aktivität.  
  
6. Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop innerhalb der <xref:System.Activities.Statements.Sequence>-Aktivität.  
  
7. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine> Aktivität nach der `PrintTransactionInfo`-Aktivität, und legen Sie deren <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client: Start Send" fest. Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Client wird hinzugefügt: Sendeaktivitäten werden gestartet.](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. Ziehen Sie eine <xref:System.ServiceModel.Activities.Send>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>-Aktivität, und legen Sie die folgenden Eigenschaften fest:  
  
    |property|Wert|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Festlegen der Send-Aktivitätseigenschaften](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. Klicken Sie auf den Link **definieren...** , und legen Sie die folgenden Einstellungen fest:  
  
     ![Meldungseinstellungen für die Send-Aktivität](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Send> Aktivität, und wählen Sie **receivereply erstellen** Die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität wird automatisch nach der <xref:System.ServiceModel.Activities.Send>-Aktivität platziert.  
  
11. Klicken Sie in der ReceiveReplyForSend-Aktivität auf den Link Definieren..., und legen Sie die folgenden Einstellungen fest:  
  
     ![Festlegen der ReceiveForSend-Meldungseinstellungen](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop zwischen der <xref:System.ServiceModel.Activities.Send>-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client: Send complete" fest.  
  
13. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client side: Reply received = " + replyMessage fest.  
  
14. Verschieben Sie eine `PrintTransactionInfo`-Aktivität per Drag &amp; Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>-Aktivität.  
  
15. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>-Aktivität per Drag &amp; Drop an das Ende des Workflows, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>-Eigenschaft auf "Client workflow ends" fest. Der abgeschlossene Clientworkflow sollte wie das folgende Diagramm aussehen.  
  
     ![Der abgeschlossene Client Workflow](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. Erstellen Sie die Projektmappe.  
  
### <a name="create-the-service-application"></a>Erstellen der Dienstanwendung  
  
1. Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Service` hinzu. Fügen Sie Verweise auf die folgenden Assemblys hinzu:  
  
    1. System.Activities.dll  
  
    2. System.ServiceModel.dll  
  
    3. System.ServiceModel.Activities.dll  
  
2. Öffnen Sie die generierte Datei Program.cs und den folgenden Code:  
  
    ```csharp
          static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3. Fügen Sie dem Projekt die folgende app.config-Datei hinzu.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a>Erstellen der Clientanwendung  
  
1. Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Client` hinzu. Fügen Sie einen Verweis auf System.Activities.dll hinzu.  
  
2. Öffnen Sie die Datei program.cs, und fügen Sie den folgenden Code hinzu.  
  
    ```csharp
    class Program  
    {  

        private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
        static void Main(string[] args)  
        {  
            //Build client  
            Console.WriteLine("Building the client.");  
            WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
            client.Completed = Program.Completed;  
            client.Aborted = Program.Aborted;  
            client.OnUnhandledException = Program.OnUnhandledException;  
            //Wait for service to start  
            Console.WriteLine("Press ENTER once service is started.");  
            Console.ReadLine();  
  
            //Start the client              
            Console.WriteLine("Starting the client.");  
            client.Run();  
            syncEvent.WaitOne();  
  
            //Sample complete  
            Console.WriteLine();  
            Console.WriteLine("Client complete. Press ENTER to exit.");  
            Console.ReadLine();  
        }  
  
        private static void Completed(WorkflowApplicationCompletedEventArgs e)  
        {  
            Program.syncEvent.Set();  
        }  
  
        private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
        {  
            Console.WriteLine("Client Aborted: {0}", e.Reason);  
            Program.syncEvent.Set();  
        }  
  
        private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
            return UnhandledExceptionAction.Cancel;  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Übersicht über Windows Communication Foundation-Transaktionen](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
