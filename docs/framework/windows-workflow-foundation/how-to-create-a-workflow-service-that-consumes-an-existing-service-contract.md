---
title: "Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]\-Funktionen verbessern die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst\-Workflowentwicklung.Das Tool für die Vertrag zuerst\-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen.Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.  
  
> [!NOTE]
>  Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst\-Workflowdiensts.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Entwicklung von Vertrag zuerst\-Workflowdiensten finden Sie unter [Entwickeln von Vertrag zuerst\-Workflowdiensten](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md).  
  
### Erstellen des Workflowprojekts  
  
1.  Wählen Sie in [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] im Menü **Datei** die Option **Neues Projekt** aus.Wählen Sie in der Struktur **Vorlagen** unter dem Knoten **C\#** die Option **WCF**aus, und wählen Sie die Vorlage **Dienstanwendung für WCF\-Workflows** aus.  
  
2.  Geben Sie für das neue Projekt den Namen `ContractFirst` ein, und klicken Sie auf **OK**.  
  
### Erstellen des Dienstvertrags  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** und dann **Neues Element** aus.Wählen Sie den Knoten **Code** auf der linken Seite und die Vorlage **Klasse** auf der rechten Seite aus.Geben Sie der neuen Klasse den Namen `IBookService`, und klicken Sie auf **OK**.  
  
2.  Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using\-Anweisung hinzu.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  Erstellen Sie das Projekt, indem Sie **STRG\+UMSCHALT\+B** drücken.  
  
### Importieren des Dienstvertrags  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstvertrag importieren** aus.Öffnen Sie unter **\<Aktuelles Projekt\>** alle untergeordneten Knoten, und wählen Sie **IBookService** aus.Klicken Sie auf **OK**.  
  
2.  Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben.Klicken Sie auf **OK**.  
  
3.  Erstellen Sie das Projekt, indem Sie **STRG\+UMSCHALT\+B** drücken, damit die importierten Aktivitäten in der Toolbox angezeigt werden.  
  
4.  Öffnen Sie im **Projektmappen\-Explorer** die Datei **Service1.xamlx**.Der Workflowdienst wird im Designer angezeigt.  
  
5.  Wählen Sie die **Sequence**\-Aktivität aus.Klicken Sie im Eigenschaftenfenster für die **ImplementedContract**\-Eigenschaft auf die Schaltfläche mit dem Auslassungszeichen \(**…**\).Klicken Sie im daraufhin angezeigten Fenster **Typauflistungs\-Editor** auf die Dropdownliste **Typ**, und wählen Sie den Eintrag **Nach Typen suchen** aus.Öffnen Sie im Dialogfeld **.NET\-Typ suchen und auswählen** unter **\<Aktuelles Projekt\>** alle untergeordneten Knoten, und wählen Sie **IBookService** aus.Klicken Sie auf **OK**.Klicken Sie im Dialogfeld **Typauflistungs\-Editor** auf **OK**.  
  
6.  Wählen Sie die **ReceiveRequest**\-Aktivität und die **SendResponse**\-Aktivität aus, und löschen Sie diese.  
  
7.  Ziehen Sie eine **Buy\_ReceiveAndSendReply**\-Aktivität und eine **Checkout\_Receive**\-Aktivität aus der Toolbox auf die **Sequenzieller Dienst**\-Aktivität.