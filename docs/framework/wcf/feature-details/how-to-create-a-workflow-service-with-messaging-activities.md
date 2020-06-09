---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: b4991fc9f8a6c45cae3943f1506247c42ed2b30b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597123"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>Vorgehensweise: Erstellen eines Workflowdiensts mit Messagingaktivitäten
In diesem Thema wird beschrieben, wie Sie mithilfe der Messagingaktivitäten einen einfachen Workflowdienst erstellen. Der Schwerpunkt des Themas liegt auf der Mechanik zum Erstellen eines Workflowdiensts. Der Dienst besteht ausschließlich aus Messagingaktivitäten. In einem realen Dienst enthält der Workflow noch viele andere Aktivitäten. Der Dienst implementiert einen Vorgang mit dem Namen "Echo", der eine Zeichenfolge verwendet und diese an den Aufrufer zurückgibt. Dieses Thema ist das erste von zwei Themen, die zusammengehören. Im nächsten Thema Gewusst [wie: Zugreifen auf einen Dienst aus einer Workflow Anwendung](how-to-access-a-service-from-a-workflow-application.md) wird erläutert, wie Sie eine Workflow Anwendung erstellen, die den in diesem Thema erstellten Dienst aufrufen kann.  
  
### <a name="to-create-a-workflow-service-project"></a>So erstellen Sie ein Workflowdienstprojekt  
  
1. Starten Sie Visual Studio 2012.  
  
2. Klicken Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt** , um das **Dialog Feld Neues Projekt**anzuzeigen. Wählen Sie aus der Liste der installierten Vorlagen und der **WCF-Workflow Dienst Anwendung** in der Liste der Projekttypen die Option **Workflow** aus. Benennen Sie das Projekt, `MyWFService` und verwenden Sie den Standard Speicherort, wie in der folgenden Abbildung dargestellt.  
  
     Klicken Sie auf **OK** , um das **Dialog Feld Neues Projekt**zu schließen.  
  
3. Nachdem das Projekt erstellt wurde, wird die Datei "Service1.xamlx" im Designer geöffnet. Dies ist in der folgenden Abbildung dargestellt.  
  
     ![Screenshot zeigt die geöffnete Datei Service1. xamlx im Designer an.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     Klicken Sie mit der rechten Maustaste auf die Aktivität **sequenzieller Dienst** , und wählen Sie **Löschen**  
  
### <a name="to-implement-the-workflow-service"></a>So implementiert Sie den Workflowdienst  
  
1. Wählen Sie auf der linken Seite des Bildschirms die Registerkarte **Toolbox** aus, um die Toolbox anzuzeigen, und klicken Sie auf die Pushpin, um das Fenster geöffnet zu lassen. Erweitern Sie den Abschnitt **Messaging** der Toolbox, um die Messaging Aktivitäten und die Vorlagen für Messaging Aktivitäten anzuzeigen, wie in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der die Toolbox mit erweitertem Messaging Abschnitt anzeigt](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. Ziehen Sie eine **receiveandsendreply** -Vorlage per Drag & amp; Drop in den Workflow-Designer. Dadurch wird eine- <xref:System.Activities.Statements.Sequence> Aktivität mit einer **Receive** -Aktivität gefolgt von einer-Aktivität erstellt, <xref:System.ServiceModel.Activities.SendReply> wie in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der die receiveandsendreply-Vorlage zeigt.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     Beachten Sie, dass die <xref:System.ServiceModel.Activities.SendReply>-Eigenschaft der <xref:System.ServiceModel.Activities.SendReply.Request%2A>-Aktivität auf `Receive` festgelegt ist, also auf den Namen der <xref:System.ServiceModel.Activities.Receive>-Aktivität, auf die die <xref:System.ServiceModel.Activities.SendReply>-Aktivität antwortet.  
  
3. Im <xref:System.ServiceModel.Activities.Receive> Aktivitätstyp in `Echo` das Textfeld mit der Bezeichnung **OperationName**. Dadurch wird der Name des Vorgangs definiert, den der Dienst implementiert.  
  
     ![Screenshot, der anzeigt, wo der Vorgangs Name angegeben wird.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. Wenn die <xref:System.ServiceModel.Activities.Receive> Aktivität ausgewählt ist, öffnen Sie das Eigenschaften Fenster, sofern dieses nicht bereits geöffnet ist, indem Sie auf das Menü **Ansicht** klicken und **Eigenschaften Fenster**auswählen. Führen Sie im **Eigenschaften Fenster** einen Bildlauf nach unten durch, bis Sie **cankreateinstance** sehen, und klicken Sie wie in der folgenden Abbildung dargestellt auf das Kontrollkästchen Mit dieser Einstellung wird es dem Workflowdiensthost ermöglicht, (bei Bedarf) eine neue Instanz des Diensts zu erstellen, wenn eine Meldung empfangen wird.  
  
     ![Screenshot mit der cankreateinzustance-Eigenschaft.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. Wählen Sie die Aktivität aus, <xref:System.Activities.Statements.Sequence> und klicken Sie in der linken unteren Ecke des Designers auf die Schaltfläche **Variablen** . Der Variablen-Editor wird angezeigt. Klicken Sie auf den Link **Variable erstellen** , um eine Variable zum Speichern der an den Vorgang gesendeten Zeichenfolge hinzuzufügen. Benennen Sie die Variable `msg` , und legen Sie den **Variablentyp** auf String fest, wie in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der zeigt, wie eine Variable hinzugefügt wird.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     Klicken Sie erneut auf die Schaltfläche **Variablen** , um den Variablen Editor zu schließen.  
  
6. Klicken Sie auf **definieren.** Verknüpfen Sie den Link im Textfeld **Inhalt** der <xref:System.ServiceModel.Activities.Receive> Aktivität, um das Dialogfeld **Inhalts Definition** anzuzeigen. Aktivieren Sie das Optionsfeld **Parameter** , klicken Sie auf den Link **neuen Parameter hinzufügen** , geben Sie `inMsg` in das Textfeld **Name** ein, wählen Sie im Dropdown-Listenfeld **Typ** die Option **Zeichenfolge** aus, und geben Sie `msg` im Textfeld **zuweisen zu** ein, wie in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der das Hinzufügen von Parameter Inhalt zeigt.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     Dadurch wird angegeben, dass die Empfangsaktivität Zeichenfolgenparameter empfängt und dass diese Daten an die `msg`-Variable gebunden werden. Klicken Sie auf **OK** , um das Dialogfeld **Inhalts Definition** zu schließen.  
  
7. Klicken Sie im Feld **Inhalt** der Aktivität auf den Link **definieren...** <xref:System.ServiceModel.Activities.SendReply> , um das Dialogfeld **Inhalts Definition** anzuzeigen. Aktivieren Sie das Optionsfeld **Parameter** , klicken Sie auf den Link **neuen Parameter hinzufügen** , geben Sie `outMsg` in das Textfeld **Name** ein, wählen Sie im Dropdown-Listenfeld **Typ** die Option **Zeichenfolge** aus, und wählen Sie im `msg` Textfeld **Wert** wie in der folgenden Abbildung dargestellt aus.  
  
     ![Screenshot, der zeigt, wie der outmsg-Parameter hinzugefügt wird.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     Dadurch wird angegeben, dass die <xref:System.ServiceModel.Activities.SendReply>-Aktivität eine Nachricht oder einen Nachrichtenvertragstyp sendet und dass die Daten an die `msg`-Variable gebunden werden. Da dies eine <xref:System.ServiceModel.Activities.SendReply>-Aktivität ist, werden die Daten von `msg` verwendet, um die von der Aktivität an den Client zurückgesendete Nachricht aufzufüllen. Klicken Sie auf **OK** , um das Dialogfeld **Inhalts Definition** zu schließen.  
  
8. Speichern und erstellen Sie die Projekt Mappe, indem Sie auf das Menü **Erstellen** klicken und Projekt Mappe **Erstellen**auswählen.  
  
## <a name="configure-the-workflow-service-project"></a>Konfigurieren des Workflowdienstprojekts  
 Der Workflowdienst wurde abgeschlossen. In diesem Abschnitt wird erklärt, wie Sie die Workflowdienstprojektmappe so konfigurieren, dass sie auf einfache Weise gehostet und ausgeführt werden kann. Diese Projektmappe verwendet den ASP.NET Development Server zum Hosten des Diensts.  
  
#### <a name="to-set-project-start-up-options"></a>So legen Sie Projektstartoptionen fest  
  
1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **mywfservice** , und wählen Sie **Eigenschaften** aus, um das Dialogfeld **Projekteigenschaften** anzuzeigen.  
  
2. Wählen Sie die Registerkarte **Web** aus, und wählen Sie unter **Start Aktion** die Option **bestimmte Seite** aus, `Service1.xamlx` wie in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der das Dialogfeld "Projekteigenschaften" anzeigt.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     Der in "Service1.xamlx" definierte Dienst wird dann unter ASP.NET Development Server gehostet.  
  
3. Drücken Sie STRG+F5, um den Dienst zu starten. Das Symbol "ASP.NET Development Server" wird in der unteren rechten Ecke des Desktops angezeigt. Dies ist in der folgenden Abbildung dargestellt.  
  
     ![Screenshot, der das Symbol "ASP.NET Developer Server" anzeigt.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     Außerdem zeigt Internet Explorer für den Dienst die Hilfeseite für WCF-Dienste an.  
  
     ![Screenshot, der die Hilfeseite für den WCF-Dienst anzeigt.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. Fahren Sie mit dem Thema Gewusst [wie: Zugreifen auf einen Dienst aus einer Workflow Anwendung](how-to-access-a-service-from-a-workflow-application.md) fort, um einen Workflow Client zu erstellen, der diesen Dienst aufruft.  
  
## <a name="see-also"></a>Weitere Informationen

- [Workflowdienste](workflow-services.md)
- [Übersicht über das Hosten von Workflowdiensten](hosting-workflow-services-overview.md)
- [Messagingaktivitäten](messaging-activities.md)
