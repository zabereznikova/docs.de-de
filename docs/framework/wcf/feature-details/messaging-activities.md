---
title: Messagingaktivitäten
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8498f215-1823-4aba-a6e1-391407f8c273
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8db31e8559d22e35f0d754a44ce425e144487296
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="messaging-activities"></a>Messagingaktivitäten
Messagingaktivitäten ermöglichen Workflows das Senden und Empfangen von WCF-Nachrichten. Indem Sie einem Workflow Messagingaktivitäten hinzufügen, können Sie beliebige komplexe Nachrichtenaustauschmuster (MEPs) modellieren.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 Es gibt drei grundlegende Nachrichtenaustauschmuster:  
  
-   **Datagramm** – beim Verwenden des Datagramms-Nachrichtenaustauschmusters sendet des Clients eine Nachricht an den Dienst, aber der Dienst antwortet nicht. Dies wird auch als "fire and forget" bezeichnet. Ein "fire and forget"-Austausch erfordert eine Out-of-Band-Bestätigung für die erfolgreiche Zustellung. Die Nachricht könnte unterwegs verloren gehen und den Dienst nicht erreichen. Wenn der Client das Senden einer Nachricht erfolgreich abgeschlossen hat, ist dies keine Garantie dafür, dass der Dienst die Nachricht erhalten hat. Das Datagramm ist ein wichtiger Baustein für das Messaging, da Sie darauf Ihre eigenen Nachrichtenaustauschmuster aufbauen können.  
  
-   **Anforderung / Antwort** : Wenn eine Nachricht an den Dienst, der Dienst führt die erforderliche Verarbeitung und sendet dann eine Antwort zurück an den Client sendet das Anforderung / Antwort-Nachrichtenaustauschmuster des Clients verwenden. Das Muster besteht aus Anforderungs-Antwort-Paaren. Beispiele für Anforderung-Antwort-Aufrufe sind Remoteprozeduraufrufe (RPC) und Browser-GET-Anforderungen. Dieses Muster wird auch als Halbduplex bezeichnet.  
  
-   **Duplex** – beim Verwenden der duplex-Nachrichtenaustauschmuster der Client und der Dienst Nachrichten miteinander in beliebiger Reihenfolge senden kann. Das Duplex-Nachrichtenaustauschmuster ist mit einem Telefongespräch vergleichbar, bei dem jedes gesprochene Wort einer Nachricht entspricht.  
  
 Mithilfe der Messagingaktivitäten können Sie diese grundlegenden Nachrichtenaustauschmuster sowie andere komplexe Nachrichtenaustauschmuster nach Belieben implementieren.  
  
## <a name="messaging-activities"></a>Messagingaktivitäten  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] definiert die folgenden Messagingaktivitäten:  
  
-   <xref:System.ServiceModel.Activities.Send> – Verwenden Sie die <xref:System.ServiceModel.Activities.Send>-Aktivität zum Senden einer Nachricht.  
  
-   <xref:System.ServiceModel.Activities.SendReply> – Verwenden Sie die <xref:System.ServiceModel.Activities.SendReply>-Aktivität zum Senden einer Antwort auf eine empfangene Nachricht. Diese Aktivität wird von Workflowdiensten beim Implementieren eines Anforderung-Antwort-Nachrichtenaustauschmusters verwendet.  
  
-   <xref:System.ServiceModel.Activities.Receive> – Verwenden Sie die <xref:System.ServiceModel.Activities.Receive>-Aktivität zum Empfangen einer Nachricht.  
  
-   <xref:System.ServiceModel.Activities.ReceiveReply> – Verwenden Sie die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität zum Empfangen einer Antwortnachricht. Diese Aktivität wird von Workflowdienstclients beim Implementieren eines Anforderung-Antwort-Nachrichtenaustauschmusters verwendet.  
  
## <a name="messaging-activities-and-message-exchange-patterns"></a>Messagingaktivitäten und Nachrichtenaustauschmuster  
 Ein Datagramm-Nachrichtenaustauschmuster umfasst einen Client, der eine Nachricht sendet, und einen Dienst, der die Nachricht empfängt. Verwenden Sie eine <xref:System.ServiceModel.Activities.Send>-Aktivität zum Senden der Nachricht, wenn der Client ein Workflow ist. Um diese Nachricht in einem Workflow zu empfangen, verwenden Sie eine <xref:System.ServiceModel.Activities.Receive>-Aktivität. Die Aktivitäten <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive> verfügen jeweils über eine Eigenschaft mit dem Namen `Content`. Diese Eigenschaft enthält die Daten, die gesendet oder empfangen werden. Beim Implementieren des Anforderung-Antwort-Nachrichtenaustauschmusters verwendet sowohl der Client als auch der Dienst Aktivitätspaare. Der Client verwendet eine <xref:System.ServiceModel.Activities.Send>-Aktivität, um die Nachricht zu senden, und eine <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität, um die Antwort vom Dienst zu empfangen. Diese zwei Aktivitäten sind einander über die <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A>-Eigenschaft zugeordnet. Diese Eigenschaft wird auf die <xref:System.ServiceModel.Activities.Send>-Aktivität festgelegt, die die ursprüngliche Nachricht gesendet hat. Der Dienst verwendet ebenfalls ein Paar zugeordneter Aktivitäten: <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply>. Diese beiden Aktivitäten werden von der <xref:System.ServiceModel.Activities.SendReply.Request%2A>-Eigenschaft zugeordnet. Diese Eigenschaft wird auf die <xref:System.ServiceModel.Activities.Receive>-Aktivität festgelegt, die die ursprüngliche Nachricht empfangen hat. Die Aktivitäten <xref:System.ServiceModel.Activities.ReceiveReply> und <xref:System.ServiceModel.Activities.SendReply> ermöglichen Ihnen wie <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive> das Senden einer <xref:System.ServiceModel.Channels.Message>-Instanz oder eines Nachrichtenvertragstyps.  
  
 Aufgrund der langen Ausführungsdauer von Workflows ist es für das Duplexmuster der Kommunikation wichtig, dass es auch Konversationen mit langer Laufzeit unterstützt. Um Konversationen mit langer Laufzeit zu unterstützen, müssen Clients, die die Konversation initiieren, dem Dienst die Möglichkeit eines Rückrufs zu einem späteren Zeitpunkt geben, sobald die Daten verfügbar sind. Eine Auftragsanforderung wird z. B. zur Genehmigung durch den Manager eingereicht. Sie wird ggf. jedoch erst nach einem Tag, einer Woche oder sogar einem Jahr verarbeitet. Der Workflow, der die Genehmigung von Bestellungen verwaltet, muss den Vorgang wiederaufnehmen können, nachdem die Genehmigung erteilt wurde. Dieses Muster der Duplexkommunikation wird in Workflows unterstützt, die die Korrelation verwenden. Um ein Duplexmuster zu implementieren, verwenden Sie die Aktivitäten <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.Receive>. Auf der <xref:System.ServiceModel.Activities.Receive> Aktivität initialisieren eine Korrelation mit den speziellen Schlüsselwert <!--zz <xref:System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName%2A>--> `System.ServiceModel.Activities.CorrelationHandle.CallbackHandleName`. Legen Sie dieses Korrelationshandle für die <xref:System.ServiceModel.Activities.Send>-Aktivität als <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A>-Eigenschaftswert fest. Weitere Informationen finden Sie unter [permanenter Duplex](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md).  
  
> [!NOTE]
>  Die dupleximplementierung des Workflows des mithilfe einer rückrufkorrelation ("permanenter Duplex") Dient zur langer Konversationen. Dies ist nicht das Gleiche wie WCF-Duplex mit Rückrufverträgen, wo die Konversation nur über eine kurze Ausführungsdauer verfügt (die Lebensdauer des Kanals).  
  
## <a name="message-formatting-and-messaging-activities"></a>Nachrichtenformatierung und Messagingaktivitäten  
 Die Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.ReceiveReply> verfügen über eine Eigenschaft mit dem Namen `Content`. Diese Eigenschaft hat den Typ <xref:System.ServiceModel.Activities.ReceiveContent> und stellt Daten dar, die die <xref:System.ServiceModel.Activities.Receive>-Aktivität oder die <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivität empfängt. .NET Framework definiert zwei verknüpfte Klassen mit den Namen <xref:System.ServiceModel.Activities.ReceiveMessageContent> und <xref:System.ServiceModel.Activities.ReceiveParametersContent>, die beide von <xref:System.ServiceModel.Activities.ReceiveContent> abgeleitet sind. Legen Sie die <xref:System.ServiceModel.Activities.Receive>-Eigenschaft der <xref:System.ServiceModel.Activities.ReceiveReply>- oder der `Content`-Aktivität auf eine Instanz einer dieser Typen fest, um Daten in einem Workflowdienst zu empfangen. Der zu verwendende Typ hängt vom Typ der Daten ab, die die Aktivität empfängt. Wenn die Aktivität ein `Message`-Objekt oder einen Nachrichtenvertragstyp empfängt, verwenden Sie <xref:System.ServiceModel.Activities.ReceiveMessageContent>. Wenn die Aktivität einen Satz von Datenvertrags- oder XML-Typen empfängt, die serialisiert werden können, verwenden Sie <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Mit <xref:System.ServiceModel.Activities.ReceiveParametersContent> können Sie mehrere Parameter senden, während Sie mit <xref:System.ServiceModel.Activities.ReceiveMessageContent> nur ein Objekt senden können, nämlich die Nachricht (bzw. den Nachrichtenvertragstyp).  
  
> [!NOTE]
>  <xref:System.ServiceModel.Activities.ReceiveMessageContent> kann auch mit einem einzelnen Datenvertrag oder XML-Typ verwendet werden, der serialisiert werden kann. Der Unterschied zwischen der Verwendung von <xref:System.ServiceModel.Activities.ReceiveParametersContent> mit einem einzelnen Parameter und dem direkten Übergeben des Objekts an <xref:System.ServiceModel.Activities.ReceiveMessageContent> ist das Übertragungsformat. Der Inhalt des Parameters wird mit einem XML-Element als Wrapper versehen, das dem Vorgangsnamen entspricht, und das serialisierte Objekt wird mit einem XML-Element als Wrapper versehen, indem der Parametername (z. B. `<Echo><msg>Hello, World</msg></Echo>`) verwendet wird. Der Meldungsinhalt weist keinen Vorgangsnamen als Wrapper auf. Stattdessen wird das serialisierte Objekt in einem XML-Element platziert, indem der Typname mit XML-Qualifizierung (z. B. `<string>Hello, World</string>`) verwendet wird.  
  
 Die Aktivitäten <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.SendReply> verfügen auch über eine Eigenschaft mit dem Namen `Content`. Diese Eigenschaft hat den Typ <xref:System.ServiceModel.Activities.SendContent> und stellt Daten dar, die die <xref:System.ServiceModel.Activities.Send>-Aktivität oder die <xref:System.ServiceModel.Activities.SendReply>-Aktivität sendet. .NET Framework definiert zwei verknüpfte Typen mit den Namen <xref:System.ServiceModel.Activities.SendMessageContent> und <xref:System.ServiceModel.Activities.SendParametersContent>, die beide von <xref:System.ServiceModel.Activities.SendContent> abgeleitet sind. Legen Sie die <xref:System.ServiceModel.Activities.Send>-Eigenschaft der <xref:System.ServiceModel.Activities.SendReply>-Aktivität oder `Content`-Aktivität auf eine Instanz mit einem dieser Typen fest, um Daten von einem Workflowdienst zu senden. Der zu verwendende Typ hängt vom Typ der Daten ab, die die Aktivität sendet. Wenn die Aktivität ein `Message`-Objekt oder einen Nachrichtenvertragstyp sendet, verwenden Sie <xref:System.ServiceModel.Activities.SendMessageContent>. Wenn die Aktivität einen Datenvertragstyp sendet, verwenden Sie <xref:System.ServiceModel.Activities.SendParametersContent>. Mit <xref:System.ServiceModel.Activities.SendParametersContent> können Sie mehrere Parameter senden, während Sie mit <xref:System.ServiceModel.Activities.SendMessageContent> nur ein Objekt senden können, nämlich die Nachricht (bzw. den Nachrichtenvertragstyp).  
  
 Falls Sie nur mithilfe der Messagingaktivitäten programmieren müssen, verwenden Sie die generischen Objekte <xref:System.Activities.InArgument%601> und <xref:System.Activities.OutArgument%601> zum Versehen der Objekte mit Wrappern, die Sie den Nachrichten- oder Parametereigenschaften der Aktivitäten <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.ReceiveReply> zuweisen. Verwendung <xref:System.Activities.InArgument%601> für die <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.SendReply> Aktivitäten und <xref:System.Activities.OutArgument%601> für <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.ReceiveReply> Aktivitäten. Für die Sendeaktivitäten werden `In`-Argumente verwendet, da die Daten an die Aktivitäten übergeben werden. Für die Empfangsaktivitäten werden `Out`-Argumente verwendet, da die Daten aus den Aktivitäten übergeben werden. Dies wird im folgenden Beispiel veranschaulicht.  
  
```  
Receive reserveSeat = new Receive  
{   
    ...   
    Content = new ReceiveParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationInfo", new OutArgument<ReservationRequest>(reservationInfo) }  
        }  
    }  
};  
SendReply reserveSeat = new SendReply  
{   
    ...   
    Request = reserveSeat,  
    Content = new SendParametersContent  
    {  
        Parameters =  
        {  
            { "ReservationId", new InArgument<string>(reservationId) }  
        }  
    },  
};  
```  
  
 Beim Implementieren eines Workflowdiensts, der einen Anforderung/Antwort-Vorgang mit void-Rückgabe definiert, müssen Sie eine <xref:System.ServiceModel.Activities.SendReply>-Aktivität instanziieren und die <xref:System.ServiceModel.Activities.SendReply.Content%2A>-Eigenschaft auf eine leere Instanz von einem der Inhaltstypen (<xref:System.ServiceModel.Activities.SendMessageContent> oder <xref:System.ServiceModel.Activities.SendParametersContent>) festlegen. Dies wird im folgenden Beispiel veranschaulicht.  
  
```  
Receive rcv = new Receive()  
{  
ServiceContractName = "IService",  
OperationName = "NullReturningContract",  
Content = new ReceiveParametersContent( new Dictionary<string, OutArgument>() { { "message", new OutArgument<string>() } } )  
};  
SendReply sr = new SendReply()  
{  
Request = rcv  
   Content = new SendParametersContent();  
};  
```  
  
## <a name="add-service-reference"></a>Dienstverweis hinzufügen  
 Beim Aufrufen eines Workflowdiensts aus einer Workflowanwendung generiert [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] benutzerdefinierte Messagingaktivitäten. Diese kapseln die üblichen <xref:System.ServiceModel.Activities.Send>-Aktivitäten und <xref:System.ServiceModel.Activities.ReceiveReply>-Aktivitäten, die in einem Anforderung-Antwort-Nachrichtenaustauschmuster verwendet werden. Verwendet diese Funktion mit der rechten Maustaste in des Clientprojekts [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] , und wählen Sie **Hinzufügen eines Dienstverweises**. Geben Sie im Adressfeld die Basisadresse des Diensts ein, und klicken Sie auf "Gehe zu". Die verfügbaren Dienste werden angezeigt, der **Services:** Feld. Erweitern Sie den Dienstknoten, um die unterstützten Verträge anzuzeigen. Wählen Sie den Vertrag, die Sie aufrufen möchten, und die Liste der verfügbaren Vorgänge wird angezeigt, der **Vorgänge** Feld. Sie können den Namespace für die generierte Aktivität angeben und klicken Sie auf **OK**. In einem Meldungsdialogfeld wird angegeben, dass der Vorgang erfolgreich abgeschlossen wurden und dass sich die generierten benutzerdefinierten Aktivitäten in der Toolbox befinden, nachdem Sie das Projekt neu erstellt haben. Für jeden im Dienstvertrag definierten Vorgang ist eine Aktivität vorhanden. Nach der Neuerstellung des Projekts können Sie die benutzerdefinierten Aktivitäten per Drag & Drop im Workflow ablegen und im Eigenschaftenfenster alle erforderlichen Eigenschaften festlegen.  
  
<!--## Messaging Activity Templates  
 To make setting up a request/response MEP on the client and service easier, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] provides two messaging activity templates. <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> is used on the service and <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> is used on the client. In both cases the templates add the appropriate messaging activities to your workflow. On the service, the <xref:System.ServiceModel.Activities.Design.ReceiveAndSendReply> adds a <xref:System.ServiceModel.Activities.Receive> activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity. The <xref:System.ServiceModel.Activities.SendReply.Request> property is automatically set to the <xref:System.ServiceModel.Activities.Receive> activity. On the client, the <xref:System.ServiceModel.Activities.Design.SendAndReceiveReply> adds a <xref:System.ServiceModel.Activities.Send> activity followed by a <xref:System.ServiceModel.Activities.ReceiveReply>. The <xref:System.ServiceModel.Activities.ReceiveReply.Request%2A> property is automatically set to the <xref:System.ServiceModel.Activities.Send> activity. To use these templates, just drag and drop the appropriate template onto your workflow.  
-->
## <a name="messaging-activities-and-transactions"></a>Messagingaktivitäten und Transaktionen  
 Wenn einen Aufruf an einen Workflowdienst ausgeführt wird, kann es ratsam sein, eine Transaktion zum Dienstvorgang auszuführen. Platzieren Sie dazu die <xref:System.ServiceModel.Activities.Receive>-Aktivität innerhalb einer <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität. Die <xref:System.ServiceModel.Activities.TransactedReceiveScope>-Aktivität enthält eine `Receive`-Aktivität und einen Textteil. Die für den Dienst ausgeführte Transaktion wird während der Ausführung des Textteils von <xref:System.ServiceModel.Activities.TransactedReceiveScope> in der Umgebung beibehalten. Die Transaktion ist abgeschlossen, wenn die Ausführung des Textteils beendet ist. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Workflows und Transaktionen finden Sie unter [Workflowtransaktionen](../../../../docs/framework/windows-workflow-foundation/workflow-transactions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zum Senden und Empfangen von Fehlern in Workflowdiensten](http://go.microsoft.com/fwlink/?LinkId=189151)  
 [Erstellen eines Workflowdiensts mit langer Ausführungszeit](../../../../docs/framework/wcf/feature-details/creating-a-long-running-workflow-service.md)
