---
title: 'Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung'
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 7375dc4f9af2eb0209b83724cd2ac9b9619b56dd
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556875"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung
In diesem Thema wird beschrieben, wie Sie einen Workflowdienst in einer Workflowkonsolenanwendung aufrufen. Dies hängt vom Abschluss des Themas Gewusst [wie: Erstellen eines Workflow Dienstanbieter mit Messaging Aktivitäten](how-to-create-a-workflow-service-with-messaging-activities.md) ab. Obwohl in diesem Thema beschrieben wird, wie ein Workflow Dienst aus einer Workflow Anwendung aufgerufen wird, können dieselben Methoden verwendet werden, um beliebige Windows Communication Foundation (WCF)-Dienste aus einer Workflow Anwendung aufzurufen.

### <a name="create-a-workflow-console-application-project"></a>Erstellen eines Workflowkonsolen-Anwendungsprojekts

1. Starten Sie Visual Studio 2012.

2. Laden Sie das mywfservice-Projekt, das Sie im Thema Gewusst [wie: Erstellen eines Workflow Dienstanbieter mit Messaging Aktivitäten](how-to-create-a-workflow-service-with-messaging-activities.md) erstellt haben.

3. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projekt Mappe **mywf** , und wählen Sie **Hinzufügen**, **Neues Projekt**. Wählen Sie in der **Konsolenanwendung** **installierte Vorlagen** und Workflows in der Liste der Projekttypen die Option **Workflow** aus. Geben Sie dem Projekt den Namen "MyWFClient", und verwenden Sie wie in der folgenden Abbildung gezeigt den Standardspeicherort.

     ![Dialogfeld "Neues Projekt hinzufügen"](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Klicken Sie zum Schließen des Dialog Felds **Neues Projekt hinzufügen**auf die Schaltfläche **OK** .

4. Nachdem das Projekt erstellt wurde, wird die Datei "Workflow1.xaml" im Designer geöffnet. Klicken Sie auf die Registerkarte **Toolbox** , um die Toolbox zu öffnen, wenn Sie nicht bereits geöffnet ist, und klicken Sie auf die PIN, um das Toolbox Fenster geöffnet zu lassen

5. Drücken Sie **STRG** + **F5** , um den Dienst zu erstellen und zu starten. Wie zuvor auch, wird der ASP.NET Development Server gestartet, und Internet Explorer zeigt die WCF-Hilfeseite an. Merken Sie sich den URI für diese Seite, da Sie diesen im nächsten Schritt verwenden.

     ![IE zeigt die WCF-Hilfeseite und den URI an](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **mywf** , und wählen Sie **Add**  >  **Dienst Verweis**hinzufügen aus. Klicken Sie auf die Schaltfläche **ermitteln** , um die aktuelle Lösung nach beliebigen Diensten zu durchsuchen. Klicken Sie in der Liste "Dienste" auf das Dreieck neben der Datei "Service1.xamlx". Klicken Sie auf das Dreieck neben "Service1", um die vom Dienst "Service1" implementierten Verträge aufzuführen. Erweitern Sie in der Liste **Dienste** den Knoten **Service1** . Der Echo-Vorgang wird in der **Vorgangs** Liste angezeigt, wie in der folgenden Abbildung dargestellt.

     ![Dialogfeld "Dienstverweis hinzufügen"](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Behalten Sie den Standard Namespace bei, und klicken Sie auf **OK** , um **Dienstverweis hinzufügen** das Dialogfeld zu schließen Das folgende Dialogfeld wird angezeigt.

     ![Dialogfeld zur Dienstverweis hinzufügen Benachrichtigung](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Klicken Sie auf **OK** , um das Dialogfeld zu schließen. Drücken Sie dann STRG+UMSCHALT+B, um die Projektmappe zu erstellen. Beachten Sie, dass in der Toolbox ein neuer Abschnitt mit dem Namen **mywfclient. ServiceReference1. Activities**hinzugefügt wurde. Erweitern Sie diesen Abschnitt, und beachten Sie die Echo-Aktivität, die wie in der folgenden Abbildung dargestellt hinzugefügt wurde.

     ![Echo Aktivität in der Toolbox](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität auf die Designeroberfläche. Sie befindet sich im Abschnitt **Ablauf Steuerung** der Toolbox.

8. <xref:System.Activities.Statements.Sequence>Klicken Sie mit der-Aktivität auf den Link **Variablen** , und fügen Sie eine Zeichen folgen Variable mit dem Namen hinzu `inString` . Weisen Sie der Variablen einen Standardwert `"Hello, world"` und eine Zeichen folgen Variable mit dem Namen zu, `outString` wie im folgenden Diagramm dargestellt.

     ![Hinzufügen einer inString-Variablen](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Ziehen Sie eine **Echo** -Aktivität per Drag & Drop in die <xref:System.Activities.Statements.Sequence> . Binden Sie im Fenster Eigenschaften das `inMsg` -Argument an die `inString` -Variable und das- `outMsg` Argument an die- `outString` Variable, wie in der folgenden Abbildung dargestellt. Dadurch wird der Wert der `inString`-Variable an den Vorgang übergeben und anschließend der Rückgabewert in die `outString`-Variable eingefügt.

     ![Binden von Argumenten an Variablen](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Ziehen Sie eine Aktivität " **Write teline** " unterhalb der **Echo** -Aktivität, um die vom Dienst--Befehl zurückgegebene Zeichenfolge anzuzeigen. Die Aktivität " **Write teline** " befindet sich im Knoten **Primitives** in der Toolbox. Binden Sie das **Text** -Argument der " **Write teline** "-Aktivität an die- `outString` Variable, indem Sie `outString` in das Textfeld der " **Write** -in"-Aktivität eingeben. Der Workflow sollte jetzt wie die folgende Abbildung aussehen.

     ![Der gesamte Clientworkflow](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Klicken Sie mit der rechten Maustaste auf die Projekt Mappe mywf, und wählen Sie **Start Projekte festlegen...** aus. Aktivieren Sie das Optionsfeld **mehrere Start Projekte** , und wählen Sie für jedes Projekt in der Spalte **Aktion** die Option **Start** aus, wie in der folgenden Abbildung dargestellt.

     ![Optionen des Startobjekts](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Drücken Sie STRG+F5, um sowohl den Dienst als auch den Client zu starten. Der ASP.NET Development Server hostet den Dienst, Internet Explorer zeigt die WCF-Hilfeseite an, und die Client Workflow Anwendung wird in einem Konsolenfenster gestartet und zeigt die vom Dienst zurückgegebene Zeichenfolge ("Hello, World") an.

## <a name="see-also"></a>Siehe auch

- [Workflowdienste](workflow-services.md)
- [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](how-to-create-a-workflow-service-with-messaging-activities.md)
- [Verwenden eines WCF-Diensts von einem Workflow in einem Webprojekt](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
