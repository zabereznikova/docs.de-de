---
title: "Transaktionsfluss in Workflowdienste und aus Workflowdiensten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Transaktionsfluss in Workflowdienste und aus Workflowdiensten
Workflowdienste und Clients können an Transaktionen teilnehmen.Damit ein Dienstvorgang Teil einer Ambient\-Transaktion wird, fügen Sie eine <xref:System.ServiceModel.Activities.Receive>\-Aktivität in eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität ein.Alle Aufrufe, die von einer <xref:System.ServiceModel.Activities.Send>\-Aktivität oder einer <xref:System.ServiceModel.Activities.SendReply>\-Aktivität in <xref:System.ServiceModel.Activities.TransactedReceiveScope> durchgeführt werden, werden auch in der Ambient\-Transaktion durchgeführt.Eine Workflowclientanwendung kann mit der <xref:System.Activities.Statements.TransactionScope>\-Aktivität eine Ambient\-Transaktion erstellen und Dienstvorgänge mithilfe der Ambient\-Transaktion aufrufen.In diesem Thema wird die Erstellung eines Workflowdiensts und Workflowclients, die an Transaktionen teilnehmen, erläutert.  
  
> [!WARNING]
>  Wenn eine Workflowdienstinstanz innerhalb einer Transaktion geladen wird und der Workflow eine <xref:System.Activities.Statements.Persist>\-Aktivität enthält, bleibt die Workflowinstanz bis zum Timeout der Transaktion hängen.  
  
> [!IMPORTANT]
>  Es wird empfohlen, bei Verwendung von <xref:System.ServiceModel.Activities.TransactedReceiveScope> alle empfangenen Nachrichten im Workflow in <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivitäten zu platzieren.  
  
> [!IMPORTANT]
>  Wenn Sie <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwenden und Nachrichten in der falschen Reihenfolge eintreffen, wird beim Versuch, die erste der Nachrichten außerhalb der normalen Reihenfolge zu übermitteln, der Workflow abgebrochen.Sie müssen sicherstellen, dass der Workflow im Leerlauf stets einen konsistenten Haltepunkt aufweist.Dies ermöglicht es Ihnen, einen abgebrochenen Workflow von einem vorherigen Persistenzpunkt neu zu starten.  
  
### Erstellen einer freigegebenen Bibliothek  
  
1.  Erstellen Sie eine neue leere Visual Studio\-Projektmappe.  
  
2.  Fügen Sie ein neues Klassenbibliotheksprojekt mit dem Namen `Common` hinzu.Fügen Sie den folgenden Assemblys Verweise hinzu:  
  
    -   System.Activities.dll  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceModel.Activities.dll  
  
    -   System.Transactions.dll  
  
3.  Fügen Sie dem `Common`\-Projekt eine neue Klasse mit dem Namen `PrintTransactionInfo` hinzu.Diese Klasse wird von <xref:System.Activities.NativeActivity> abgeleitet und überlädt die <xref:System.Activities.NativeActivity.Execute%2A>\-Methode.  
  
    ```  
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
  
     Diese systemeigene Aktivität, in der Informationen zur Ambient\-Transaktion angezeigt werden, wird in den in diesem Thema verwendeten Dienst\- und Clientworkflows eingesetzt.Erstellen Sie die Projektmappe, um diese Aktivität im Abschnitt **Allgemein** der **Toolbox** verfügbar zu machen.  
  
### Implementieren des Workflowdiensts  
  
1.  Fügen Sie einen neuen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Workflowdienst mit dem Namen `WorkflowService` zum `Common`\-Projekt hinzu.Klicken Sie hierzu mit der rechten Maustaste auf das `Common`\-Projekt, und wählen Sie **Hinzufügen** und **Neues Element ...** aus. Klicken Sie dann unter **Installierte Vorlagen** auf **Workflow**, und wählen Sie den WCF\-Workflowdienst.  
  
     ![Hinzufügen eines Workflowdiensts](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")  
  
2.  Löschen Sie die `ReceiveRequest`\-Standardaktivität und `SendResponse`\-Standardaktivität.  
  
3.  Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität in die `Sequential Service`\-Aktivität.Legen Sie die Texteigenschaft auf `"Workflow Service starting ..."` fest, wie im folgenden Beispiel gezeigt.  
  
     ![Hinzufügen einer WriteLine&#45;Aktivität](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")  
  
4.  Verschieben Sie eine <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>\-Aktivität.Die <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität befindet sich im Abschnitt **Messaging** der **Toolbox**.Die <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität besteht aus zwei Abschnitten: **Anforderung** und **Text**.Der Abschnitt **Anforderung** enthält die <xref:System.ServiceModel.Activities.Receive>\-Aktivität.Der Abschnitt **Text** enthält die Aktivitäten, die in einer Transaktion ausgeführt werden, nachdem eine Nachricht empfangen wurde.  
  
     ![Hinzufügen einer TransactedReceiveScope&#45;Aktivität](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")  
  
5.  Wählen Sie die <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität aus, und klicken Sie auf die Schaltfläche **Variablen**.Fügen Sie die folgenden Variablen hinzu:  
  
     ![Hinzufügen von Variablen zu TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")  
  
    > [!NOTE]
    >  Sie können die standardmäßig vorhandene Datenvariable löschen.Sie können auch die vorhandene Handlevariable verwenden.  
  
6.  Verschieben Sie eine <xref:System.ServiceModel.Activities.Receive>\-Aktivität per Drag & Drop im Abschnitt **Anforderung** der <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität.Legen Sie die folgenden Eigenschaften fest:  
  
    |Eigenschaft|Wert|  
    |-----------------|----------|  
    |CanCreateInstance|Wahr \(aktivieren Sie das Kontrollkästchen\)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Der Workflow müsste wie folgt aussehen:  
  
     ![Hinzufügen einer Receive&#45;Aktivität](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")  
  
7.  Klicken Sie in der <xref:System.ServiceModel.Activities.Receive>\-Aktivität auf den Link **Definieren...**, und legen Sie die folgenden Einstellungen fest:  
  
     ![Festlegen von Meldungseinstellungen für die Receive&#45;Aktivität](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")  
  
8.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>\-Aktivität per Drag & Drop in den Textabschnitt vom <xref:System.ServiceModel.Activities.TransactedReceiveScope>.Verschieben Sie innerhalb der <xref:System.Activities.Statements.Sequence>\-Aktivität zwei <xref:System.Activities.Statements.WriteLine>\-Aktivitäten per Drag & Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaften wie in der folgenden Tabelle gezeigt fest.  
  
    |Aktivität|Value|  
    |---------------|-----------|  
    |1. WriteLine|“Service: Receive Completed”|  
    |2. WriteLine|"Service: Received \= " \+ requestMessage|  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Hinzufügen von WriteLine&#45;Aktivitäten](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")  
  
9. Ziehen Sie die `PrintTransactionInfo`\-Aktivität per Drag & Drop an die Stelle nach der zweiten <xref:System.Activities.Statements.WriteLine>\-Aktivität im **Text** in der <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Aktivität.  
  
     ![Nach dem Hinzufügen von PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")  
  
10. Ziehen Sie eine <xref:System.Activities.Statements.Assign>\-Aktivität per Drag & Drop an die Stelle nach der `PrintTransactionInfo`\-Aktivität, und legen Sie die Eigenschaften entsprechend der folgenden Tabelle fest.  
  
    |Eigenschaft|Wert|  
    |-----------------|----------|  
    |An|replyMessage|  
    |Wert|"Service: Sending reply."|  
  
11. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>\-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf "Service: Begin reply" fest.  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Nach dem Hinzufügen von Assign und WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")  
  
12. Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive>\-Aktivität, wählen Sie **SendReply erstellen** aus, und fügen Sie die Option nach der letzten <xref:System.Activities.Statements.WriteLine>\-Aktivität ein.Klicken Sie in der `SendReplyToReceive`\-Aktivität auf den Link **Definieren...**, und legen Sie die folgenden Einstellungen fest.  
  
     ![Einstellungen der Antwortmeldung](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")  
  
13. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an die Stelle nach der `SendReplyToReceive`\-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf "Service: Reply sent” fest.  
  
14. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an das Ende des Workflows, und legen Sie die Eigenschaft <xref:System.Activities.Statements.WriteLine.Text%2A> auf "Service: Workflow ends, press ENTER to exit" fest.  
  
     Der abgeschlossene Dienstworkflow müsste wie folgt aussehen:  
  
     ![Vollständiger Serviceworkflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")  
  
### Implementieren des Workflowclients  
  
1.  Fügen Sie eine neue WCF\-Workflowanwendung mit dem Namen `WorkflowClient` zum `Common`\-Projekt hinzu.Klicken Sie hierzu mit der rechten Maustaste auf das `Common`\-Projekt, und wählen Sie **Hinzufügen** und **Neues Element ...** aus. Klicken Sie dann unter **Installierte Vorlagen** auf **Workflow**, und wählen Sie **Aktivität**.  
  
     ![Aktivitätsprojekt hinzufügen](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")  
  
2.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>\-Aktivität per Drag & Drop auf die Entwurfsoberfläche.  
  
3.  Verschieben Sie in der <xref:System.Activities.Statements.Sequence>\-Aktivität eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf `"Client: Workflow starting"` fest.Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Eine WriteLine&#45;Aktivität hinzufügen](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")  
  
4.  Verschieben Sie eine <xref:System.Activities.Statements.TransactionScope>\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>\-Aktivität.Wählen Sie die <xref:System.Activities.Statements.TransactionScope>\-Aktivität aus, klicken Sie auf die Schaltfläche Variablen, und fügen Sie die folgenden Variablen hinzu.  
  
     ![Variablen zu TransactionScope hinzufügen](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")  
  
5.  Ziehen Sie eine <xref:System.Activities.Statements.Sequence>\-Aktivität per Drag & Drop in den Text der <xref:System.Activities.Statements.TransactionScope>\-Aktivität.  
  
6.  Verschieben Sie eine `PrintTransactionInfo`\-Aktivität per Drag & Drop innerhalb der <xref:System.Activities.Statements.Sequence>\-Aktivität.  
  
7.  Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an die Stelle nach der `PrintTransactionInfo`\-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf “Client: Beginning Send” fest.Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Hinzufügen von Aktivitäten](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")  
  
8.  Ziehen Sie eine <xref:System.ServiceModel.Activities.Send>\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.Assign>\-Aktivität, und legen Sie die folgenden Eigenschaften fest:  
  
    |Eigenschaft|Wert|  
    |-----------------|----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Der Workflow müsste jetzt wie folgt aussehen:  
  
     ![Festlegen der Send&#45;Aktivitätseigenschaften](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")  
  
9. Klicken Sie auf den Link **Definieren...**, und legen Sie die folgenden Einstellungen fest:  
  
     ![Meldungseinstellungen für die Send&#45;Aktivität](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")  
  
10. Klicken Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Send>\-Aktivität, und wählen Sie **ReceiveReply erstellen** aus.Die <xref:System.ServiceModel.Activities.ReceiveReply>\-Aktivität wird automatisch nach der <xref:System.ServiceModel.Activities.Send>\-Aktivität platziert.  
  
11. Klicken Sie auf den Link Definieren…in der ReceiveReplyForSend\-Aktivität, und legen Sie die folgenden Einstellungen fest:  
  
     ![Festlegen der ReceiveForSend&#45;Meldungseinstellungen](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")  
  
12. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop zwischen der <xref:System.ServiceModel.Activities.Send>\-Aktivität und der <xref:System.ServiceModel.Activities.ReceiveReply>\-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf "Client: Send complete" fest.  
  
13. Ziehen Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.ServiceModel.Activities.ReceiveReply>\-Aktivität, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf "Client side: Reply received \= " \+ replyMessage fest.  
  
14. Verschieben Sie eine `PrintTransactionInfo`\-Aktivität per Drag & Drop an die Stelle nach der <xref:System.Activities.Statements.WriteLine>\-Aktivität.  
  
15. Verschieben Sie eine <xref:System.Activities.Statements.WriteLine>\-Aktivität per Drag & Drop an das Ende des Workflows, und legen Sie die <xref:System.Activities.Statements.WriteLine.Text%2A>\-Eigenschaft auf "Client workflow ends" fest. Der abgeschlossene Clientworkflow sollte wie das folgende Diagramm aussehen.  
  
     ![Der abgeschlossene Clientworkflow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")  
  
16. Erstellen Sie die Projektmappe.  
  
### Erstellen der Dienstanwendung  
  
1.  Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Service` hinzu.Fügen Sie den folgenden Assemblys Verweise hinzu:  
  
    1.  System.Activities.dll  
  
    2.  System.ServiceModel.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
2.  Öffnen Sie die generierte Datei Program.cs und den folgenden Code:  
  
    ```  
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
  
3.  Fügen Sie dem Projekt die folgende app.config\-Datei hinzu.  
  
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
  
### Erstellen der Clientanwendung  
  
1.  Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `Client` hinzu.Fügen Sie einen Verweis auf System.Activities.dll hinzu.  
  
2.  Öffnen Sie die Datei program.cs, und fügen Sie den folgenden Code hinzu.  
  
    ```  
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
  
## Siehe auch  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Übersicht über Windows Communication Foundation\-Transaktionen](../../../../docs/framework/wcf/feature-details/transactions-overview.md)   
 [Verwendung von TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)