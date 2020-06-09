---
title: Erstellen eines Workflowdiensts mit langer Ausführungszeit
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 4ae01201230bf848c045158424db60097d8dd767
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599346"
---
# <a name="create-a-long-running-workflow-service"></a>Erstellen eines Workflow Dienstanbieter mit langer Laufzeit

In diesem Thema wird beschrieben, wie ein Workflowdienst mit langer Laufzeit erstellt wird. Workflowdienste mit langer Laufzeit können über einen sehr großen Zeitraum hinweg ausgeführt werden. Währenddessen kann der Workflow in den Leerlauf wechseln und auf weitere Informationen warten. In diesem Fall wird der Workflow in einer SQL-Datenbank beibehalten und aus dem Arbeitsspeicher entfernt. Wenn weitere Informationen für die Workflowinstanz verfügbar sind, wird diese wieder in den Arbeitsspeicher geladen, und die Ausführung wird fortgesetzt.  In diesem Szenario implementieren Sie ein stark vereinfachtes Bestellsystem.  Zunächst wird eine Nachricht vom Client an den Workflow gesendet, um die Bestellung zu beginnen. Die Bestell-ID wird an den Client zurückgegeben. Der Workflowdienst wartet nun auf eine weitere Nachricht vom Client, wechselt in den Leerlauf und wird in der SQL-Datenbank beibehalten.  Wenn die nächste Nachricht vom Client mit der Bestellung eines Artikels empfangen wird, wird der Workflowdienst wieder in den Arbeitsspeicher geladen, und die Bestellung wird abschließend bearbeitet. In diesem Codebeispiel wird eine Zeichenfolge zurückgegeben, die angibt, dass der Artikel der Bestellung hinzugefügt wurde. Das Codebeispiel ist nicht als reale Anwendung der Technologie gedacht. Es soll vielmehr auf einfache Weise einen Workflowdienst mit langer Laufzeit veranschaulichen. In diesem Thema wird davon ausgegangen, dass Sie wissen, wie Visual Studio 2012-Projekte und-Lösungen erstellt werden

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen folgende Software installiert haben, um diese exemplarische Vorgehensweise verwenden zu können:

1. Microsoft SQL Server 2008

2. Visual Studio 2012

3. Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]

4. Sie sind mit WCF und Visual Studio 2012 vertraut und wissen, wie Projekte/Projektmappen erstellt werden.

## <a name="set-up-the-sql-database"></a>Einrichten der SQL-Datenbank

1. Damit Workflowdienstinstanzen beibehalten werden können, muss Microsoft SQL Server installiert sein, und Sie müssen eine Datenbank konfiguriert haben, in der die beibehaltenen Workflowinstanzen gespeichert werden können. Klicken Sie auf die Schaltfläche **Start** , und wählen Sie **Alle Programme**, **Microsoft SQL Server 2008**und **Microsoft SQL Management Studio**aus, um Microsoft SQL Management Studio auszuführen.

2. Klicken Sie auf die Schaltfläche **verbinden** , um sich bei der SQL Server Instanz anzumelden.

3. Klicken Sie in der Strukturansicht mit der rechten Maustaste auf **Datenbanken** , und wählen Sie **neue Datenbank** zum Erstellen einer neuen Datenbank mit dem Namen `SQLPersistenceStore` .

4. Führen Sie die Skriptdatei SqlWorkflowInstanceStoreSchema.sql unter C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en in der SQLPersistenceStore-Datenbank aus, um die erforderlichen Datenbankschemas einzurichten.

5. Führen Sie die Skriptdatei SqlWorkflowInstanceStoreLogic.sql unter C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en in der SQLPersistenceStore-Datenbank aus, um die erforderliche Datenbanklogik einzurichten.

## <a name="create-the-web-hosted-workflow-service"></a>Erstellen des webgehosteten Workflow Diensts

1. Erstellen Sie eine leere Visual Studio 2012-Projekt Mappe, und benennen Sie Sie `OrderProcessing` .

2. Fügen Sie der Projektmappe ein neues Projekt für eine WCF-Workflowdienstanwendung mit dem Namen `OrderService` hinzu.

3. Wählen Sie im Dialogfeld Projekteigenschaften die Registerkarte **Web** aus.

    1. Wählen Sie unter **Start Aktion** **bestimmte Seite** aus, und geben Sie an `Service1.xamlx` .

        ![Workflowdienstprojekt-Webeigenschaften](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Erstellen der Dienst spezifischen Seiten Option für den webgehosteten Workflow")

    2. Wählen Sie unter **Server** die Option **lokalen IIS-Webserver verwenden**aus.

        ![Lokale Webservereinstellungen](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Erstellen des webgehosteten Workflow Diensts-Option "lokalen IIS-Webserver verwenden"")

        > [!WARNING]
        > Sie müssen Visual Studio 2012 im Administrator Modus ausführen, um diese Einstellung vorzunehmen.

        Mit diesen beiden Schritten wird das Workflowdienstprojekt konfiguriert, das von IIS gehostet werden soll.

4. Öffnen `Service1.xamlx` Sie, wenn es nicht bereits geöffnet ist, und löschen Sie die vorhandenen Aktivitäten **ReceiveRequest** und **SendResponse** .

5. Wählen Sie die Aktivität **sequenzieller Dienst** aus, klicken Sie auf den Link **Variablen** , und fügen Sie die in der folgenden Abbildung gezeigten Variablen hinzu Dadurch werden einige Variablen hinzugefügt, die im weiteren Verlauf in diesem Workflow verwendet werden.

    > [!NOTE]
    > Wenn correlationhandle nicht in der Dropdown Liste Variablentyp angezeigt wird, wählen Sie in der Dropdown Liste die Option **nach Typen suchen** aus. Geben Sie correlationhandle in das Feld **Typname** ein, wählen Sie correlationhandle aus dem Listenfeld aus, und klicken Sie auf **OK**.

    ![Variablen hinzufügen](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Fügen Sie der sequenziellen Dienst Aktivität Variablen hinzu.")

6. Ziehen Sie eine **receiveandsendreply** -Aktivitäts Vorlage per Drag & Drop in die Aktivität **sequenzieller Dienst** . Diese Gruppe von Aktivitäten empfängt eine Nachricht von einem Client und sendet eine Antwort.

    1. Wählen Sie die **Receive** -Aktivität aus, und legen Sie die in der folgenden Abbildung markierten Eigenschaften fest.

        ![Receive-Aktivitätseigenschaften festlegen](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Legen Sie die Eigenschaften der Empfangs Aktivität fest.")

        Mit der DisplayName-Eigenschaft wird der angezeigte Name für die Receive-Aktivität im Designer festgelegt. Mit der ServiceContractName-Eigenschaft und der OperationName-Eigenschaft wird der Name des Dienstvertrags und des Vorgangs angegeben, die von der Receive-Aktivität implementiert werden. Weitere Informationen zur Verwendung von Verträgen in Workflow Diensten finden Sie unter [Verwenden von Verträgen im Workflow](using-contracts-in-workflow.md).

    2. Klicken Sie in der **receivestartor der** -Aktivität auf den Link **definieren...** , und legen Sie die Eigenschaften fest, die in der folgenden Abbildung dargestellt sind.  Beachten Sie, dass das Optionsfeld **Parameter** ausgewählt ist, dass ein Parameter `p_customerName` mit dem Namen an die Variable gebunden ist `customerName` . Dadurch wird die **Receive** -Aktivität konfiguriert, um einige Daten zu empfangen und diese Daten an lokale Variablen zu binden.

        ![Festlegen der von der Receive-Aktivität empfangenen Daten](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Legen Sie die Eigenschaften für die von der Receive-Aktivität empfangenen Daten fest.")

    3. Wählen Sie die **sendreplytor eceive** -Aktivität aus, und legen Sie die in der folgenden Abbildung gezeigte hervorgehobene Eigenschaft fest.

        ![Festlegen der Eigenschaften der SendReply-Aktivität](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")

    4. Klicken Sie in der **sendreplyderstartor** -Aktivität auf den Link **definieren...** , und legen Sie die Eigenschaften fest, die in der folgenden Abbildung dargestellt sind. Beachten Sie, dass das Optionsfeld **Parameter** ausgewählt ist. ein Parameter `p_orderId` mit dem Namen ist an die `orderId` Variable gebunden. Mit dieser Einstellung wird festgelegt, dass von der SendReplyToStartOrder-Aktivität ein Wert vom Typ Zeichenfolge an den Aufrufer zurückgegeben wird.

        ![Konfigurieren der SendReply-Aktivitätsinhaltsdaten](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Einstellung für die Aktivität "Aktivität festlegen"")

    5. Ziehen Sie eine Assign-Aktivität per Drag & Drop zwischen den **Receive** -und **SendReply** -Aktivitäten, und legen Sie die Eigenschaften wie in der folgenden Abbildung dargestellt fest:

        ![Hinzufügen einer Zuweisungsaktivität](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Fügen Sie eine Assign-Aktivität hinzu.")

        Dadurch wird eine neue Bestell-ID erstellt, und der Wert wird in der orderId-Variablen platziert.

    6. Wählen Sie die Aktivität **ReplyTo startor der** aus. Klicken Sie im Eigenschaften Fenster auf die Schaltfläche mit den Auslassungs Punkten für **correlationinitializers**. Wählen Sie den Link **Initialisierer hinzufügen** aus, geben Sie `orderIdHandle` in das Textfeld Initialisierer ein, wählen Sie als Korrelationstyp Abfrage korrelationsinitialisierer aus, und wählen Sie p_orderId im Dropdown Feld XPath-Abfragen aus. Diese Einstellungen werden in der folgenden Abbildung gezeigt. Klicken Sie auf **OK**.  Dadurch wird eine Korrelation zwischen dem Client und dieser Instanz des Workflowdiensts initialisiert. Wenn eine Nachricht mit dieser Bestell-ID empfangen wird, wird sie an diese Instanz des Workflowdiensts weitergeleitet.

        ![Hinzufügen eines Korrelationsinitialisierers](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Fügen Sie einen korrelationsinitialisierer hinzu.")

7. Ziehen Sie eine andere **receiveandsendreply** -Aktivität per Drag & Drop an das Ende des Workflows (außerhalb der **Sequenz** , in der die ersten **Receive** -und **SendReply** -Aktivitäten enthalten sind). Dadurch wird die zweite Meldung empfangen, die vom Client gesendet wurde, und beantwortet.

    1. Wählen Sie die **Sequenz** mit den neu hinzugefügten **Receive** -und **SendReply** -Aktivitäten aus, und klicken Sie auf die Schaltfläche **Variablen** Fügen Sie die in der folgenden Abbildung hervorgehobene Variable hinzu:

        ![Hinzufügen von neuen Variablen](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Fügen Sie die Itemid-Variable hinzu.")

        Fügen Sie außerdem `orderResult` als **Zeichenfolge** im `Sequence` Bereich hinzu.

    2. Wählen Sie die **Receive** -Aktivität aus, und legen Sie die in der folgenden Abbildung gezeigten Eigenschaften fest:

        ![Festlegen der Eigenschaften der Empfangs Aktivität](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Legen Sie die Eigenschaften der Empfangs Aktivitäten fest.")

        > [!NOTE]
        > Vergessen Sie nicht, das **servicecontractname** -Feld mit zu ändern `../IAddItem` .

    3. Klicken Sie in der **receiveadditem** -Aktivität auf den Link **definieren...** , und fügen Sie die in der folgenden Abbildung gezeigten Parameter hinzu: Dadurch wird die Receive-Aktivität so konfiguriert, dass zwei Parameter, die Bestell-ID und die ID des bestellten Elements akzeptiert werden.

        ![Angeben von Parametern für den zweiten Empfang](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Konfigurieren Sie die Receive-Aktivität, um zwei Parameter zu empfangen.")

    4. Klicken Sie auf die Schaltfläche **correlateon** Auslassungs Punkte, und geben Sie ein `orderIdHandle` . Klicken Sie unter **XPath-Abfragen**auf den Dropdown Pfeil, und wählen Sie aus `p_orderId` . Dadurch wird die Korrelation für die zweite Receive-Aktivität konfiguriert. Weitere Informationen zur Korrelation finden Sie unter [Korrelation](correlation.md).

        ![Festlegen der CorrelatesOn-Eigenschaft](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Legen Sie die CorrelatesOn-Eigenschaft fest.")

    5. Ziehen Sie eine **if** -Aktivität direkt nach der **receiveadditem** -Aktivität per Drag & Drop. Diese Aktivität verhält sich analog zu einer Anweisung.

        1. Legen Sie die **Condition** -Eigenschaft auf fest`itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`

        2. Ziehen Sie eine **assign** -Aktivität in den Abschnitt **Then** und einen weiteren in den Abschnitt **else** , und legen Sie die Eigenschaften der **assign** -Aktivitäten fest, wie in der folgenden Abbildung dargestellt.

            ![Zuweisen des Ergebnisses des Dienstaufrufs](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Weisen Sie das Ergebnis des Dienst Aufrufes zu.")

            Wenn die Bedingung ist, `true` wird der **Then** -Abschnitt ausgeführt. Wenn die Bedingung ist, `false` wird der **else** -Abschnitt ausgeführt.

        3. Wählen Sie die **sendreplytor eceive** -Aktivität aus, und legen Sie die **Display Name** -Eigenschaft fest, wie in der folgenden Abbildung dargestellt.

            ![Festlegen der SendReply-Aktivitätseigenschaften](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Legen Sie die SendReply-Aktivitäts Eigenschaft fest.")

        4. Klicken Sie in der Aktivität " **streplyshadditem** " auf den Link **definieren...** , und konfigurieren Sie ihn wie in der folgenden Abbildung dargestellt. Dadurch wird die **sendreplythadditem** -Aktivität so konfiguriert, dass der Wert in der Variablen zurückgegeben wird `orderResult` .

            ![Festlegen der Datenbindung für die SendReply-Aktivität](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Legen Sie die Eigenschaft für die sendreplythadditem-Aktivität fest.")

8. Öffnen Sie die Datei Web. config, und fügen Sie im Abschnitt die folgenden Elemente hinzu \<behavior> , um die Workflow Persistenz zu aktivieren.

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    > Ersetzen Sie den Namen des Hosts und der SQL Server-Instanz aus dem vorherigen Codeausschnitt.

9. Erstellen Sie die Projektmappe.

## <a name="create-a-client-application-to-call-the-workflow-service"></a>Erstellen Sie eine Client Anwendung, um den Workflow Dienst aufzurufen.

1. Fügen Sie der Projektmappe ein neues Konsolenanwendungsprojekt mit dem Namen `OrderClient` hinzu.

2. Fügen Sie dem `OrderClient`-Projekt Verweise auf die folgenden Assemblys hinzu:

    1. System.ServiceModel.dll

    2. System.ServiceModel.Activities.dll

3. Fügen Sie dem Workflowdienst einen Dienstverweis hinzu, und geben Sie `OrderService` als Namespace an.

4. Fügen Sie der `Main()`-Methode des Clientprojekts den folgenden Code hinzu:

    ```csharp
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5. Erstellen Sie die Projektmappe, und führen Sie die `OrderClient`-Anwendung aus. Der folgende Text wird vom Client angezeigt:

    ```output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. Um zu überprüfen, ob der Workflow Dienst persistent gespeichert wurde, starten Sie den SQL Server Management Studio, indem Sie im **Startmenü** **Alle Programme**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**auswählen.

    1. Erweitern Sie im linken Bereich, **Datenbanken**, **sqlpersistencestore**, **views** , und klicken Sie mit der rechten Maustaste auf **System. Activities. DurableInstancing. Instanzen** , und wählen Sie **oberste 1000 Zeilen auswählen**aus. Vergewissern Sie sich im **Ergebnis** Bereich, dass mindestens eine Instanz aufgeführt ist. Es kann sein, dass auch Instanzen früherer Ausführungen aufgelistet sind, wenn Fehler bei der Ausführung aufgetreten sind. Sie können vorhandene Zeilen löschen, indem Sie mit der rechten Maustaste auf **System. Activities. DurableInstancing. Instance** klicken und **Oberste 200 Zeilen bearbeiten**auswählen, auf die Schaltfläche **Ausführen** klicken, alle Zeilen im Ergebnisbereich auswählen und dann **Löschen**auswählen.  Um zu überprüfen, ob in der Datenbank die Instanz angezeigt wird, die von Ihrer Anwendung erstellt wurde, können Sie überprüfen, ob die Ansicht für Instanzen vor Ausführung des Clients leer ist. Führen Sie die Abfrage (Oberste 1000 Zeilen auswählen) erneut aus, sobald der Client ausgeführt wird, und überprüfen Sie, ob eine neue Instanz hinzugefügt wurde.

7. Drücken Sie die EINGABETASTE, um die Nachricht zum Hinzufügen des Artikels an den Workflowdienst zu senden. Der folgende Text wird vom Client angezeigt:

    ```output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a>Weitere Informationen

- [Workflowdienste](workflow-services.md)
