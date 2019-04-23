---
title: 'Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung'
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 178fb04244cb3e5075722877fdd3e2b5a92b8502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309315"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a>Vorgehensweise: Zugreifen auf einen Dienst aus einer Workflowanwendung
In diesem Thema wird beschrieben, wie Sie einen Workflowdienst in einer Workflowkonsolenanwendung aufrufen. Es setzt das Ende der [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) Thema. Obwohl in diesem Thema wird beschrieben, wie Sie einen Workflowdienst aus einer workflowanwendung aufrufen, können die gleichen Methoden verwendet werden, um einen Windows Communication Foundation (WCF)-Dienst aus einer workflowanwendung aufrufen.

### <a name="create-a-workflow-console-application-project"></a>Erstellen eines Workflowkonsolen-Anwendungsprojekts

1. Starten Sie Visual Studio 2012.

2. Laden Sie das MyWFService-Projekt, das Sie erstellt, in haben der [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) Thema.

3. Klicken Sie mit der rechten Maustaste auf die **MyWFService** -Lösung in die **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Projekt**. Wählen Sie **Workflow** in die **installierte Vorlagen** und **Konsolenanwendung für Workflows** aus der Liste der Projekttypen zur Verfügung. Geben Sie dem Projekt den Namen "MyWFClient", und verwenden Sie wie in der folgenden Abbildung gezeigt den Standardspeicherort.

     ![Dialogfeld "Neues Projekt hinzufügen"](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     Klicken Sie auf die **OK** Schaltfläche zum Schließen der **neue Projektdialogfeld hinzufügen**.

4. Nachdem das Projekt erstellt wurde, wird die Datei "Workflow1.xaml" im Designer geöffnet. Klicken Sie auf die **Toolbox** Tab, um die Toolbox zu öffnen, ist dies nicht bereits geöffnet, und klicken Sie auf das Pinsymbol, damit das Toolboxfenster geöffnet bleibt.

5. Drücken Sie **STRG**+**F5** zum Erstellen und starten Sie den Dienst. Wie zuvor auch, wird der ASP.NET Development Server gestartet, und Internet Explorer zeigt die WCF-Hilfeseite an. Merken Sie sich den URI für diese Seite, da Sie diesen im nächsten Schritt verwenden.

     ![Internet Explorer zum Anzeigen von WCF-Hilfeseite und URI](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. Klicken Sie mit der rechten Maustaste auf die **"mywfclient"** -Projekt in der **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **Dienstverweis**. Klicken Sie auf die **Discover** Schaltfläche, um die aktuelle Projektmappe nach Diensten suchen. Klicken Sie in der Liste "Dienste" auf das Dreieck neben der Datei "Service1.xamlx". Klicken Sie auf das Dreieck neben "Service1", um die vom Dienst "Service1" implementierten Verträge aufzuführen. Erweitern Sie die **"Service1"** Knoten in der **Services** Liste. Die Echo-Vorgang wird angezeigt, der **Vorgänge** Liste wie in der folgenden Abbildung dargestellt.

     ![Dialogfeld "Dienstverweis hinzufügen"](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     Behalten Sie den Standardnamespace, und klicken Sie auf **OK** zum Verwerfen der **Hinzufügen eines Dienstverweises** Dialogfeld. Das folgende Dialogfeld wird angezeigt.

     ![Dienst-Verweisbenachrichtigung-Dialogfeld "hinzufügen"](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     Klicken Sie auf **OK** um das Dialogfeld zu schließen. Drücken Sie dann STRG+UMSCHALT+B, um die Projektmappe zu erstellen. Beachten Sie, dass in der Toolbox ein neuer Abschnitt hinzugefügt wurde aufgerufen **MyWFClient.ServiceReference1.Activities**. Erweitern Sie diesen Abschnitt, und beachten Sie die Echo-Aktivität, die wie in der folgenden Abbildung dargestellt hinzugefügt wurde.

     ![Echoaktivität in der toolbox](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. Ziehen Sie eine <xref:System.Activities.Statements.Sequence>-Aktivität auf die Designeroberfläche. Es befindet sich unter dem **Ablaufsteuerung** Abschnitt der Toolbox.

8. Mit der <xref:System.Activities.Statements.Sequence> -Aktivität in den Fokus besitzt, klicken Sie auf die **Variablen** verknüpfen, und fügen Sie eine Zeichenfolgenvariable mit dem Namen `inString`. Geben Sie der Variable den Standardwert `"Hello, world"` sowie eine String-Variable, die mit dem Namen `outString` wie im folgenden Diagramm dargestellt.

     ![Hinzufügen einer InString-Variablen](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. Drag & drop eine **Echo** Aktivität in der <xref:System.Activities.Statements.Sequence>. Binden Sie im Eigenschaftenfenster die `inMsg` Argument für die `inString` Variable und die `outMsg` Argument für die `outString` -Variable, wie in der folgenden Abbildung dargestellt. Dadurch wird der Wert der `inString`-Variable an den Vorgang übergeben und anschließend der Rückgabewert in die `outString`-Variable eingefügt.

     ![Binden von Argumenten an Variablen](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. Drag & drop eine **WriteLine** Aktivität unten die **Echo** Aktivität, um die vom Dienstaufruf zurückgegebene Zeichenfolge anzuzeigen. Die **WriteLine** Aktivität befindet sich in der **primitive** Knoten in der Toolbox. Binden der **Text** Argument der **WriteLine** Aktivität, um die `outString` Variable durch Eingabe `outString` in das Textfeld auf die **WriteLine** Aktivität. Der Workflow sollte jetzt wie die folgende Abbildung aussehen.

     ![Der gesamte Clientworkflow](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. Mit der rechten Maustaste in der Projektmappe "mywfservice", und wählen Sie **Startprojekte festlegen...** . Wählen Sie die **mehrere Startprojekte** Optionsfeld, und wählen **starten** für jedes Projekt in der **Aktion** Spalte wie in der folgenden Abbildung gezeigt.

     ![Optionen des Startobjekts](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. Drücken Sie STRG+F5, um sowohl den Dienst als auch den Client zu starten. Der ASP.NET Development Server hostet den Dienst, Internet Explorer wird angezeigt, die WCF-Hilfeseite und die Workflow-Clientanwendung wird in einem Konsolenfenster gestartet und zeigt die Zeichenfolge, die vom Dienst ("Hello, World") zurückgegeben.

## <a name="see-also"></a>Siehe auch

- [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)
- [Verarbeiten eines WCF-Diensts aus einem Workflow in einem Webprojekt](https://go.microsoft.com/fwlink/?LinkId=207725)
