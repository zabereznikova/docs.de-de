---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 05c59bde424049eb5bef8f8bd09c472b58eaa9ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248824"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags

.NET Framework 4,5 bietet eine bessere Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflow Entwicklung. Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen. Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.  
  
> [!NOTE]
> Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts. Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Diensten finden Sie unter [Contract First Workflow Service Development](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Erstellen des Workflowprojekts  
  
1. Wählen Sie in Visual Studio **Datei** und **Neues Projekt** aus. Wählen Sie in der **Vorlagen** Struktur unter dem Knoten **c#** den **WCF** -Knoten aus, und wählen Sie die Vorlage **WCF-Workflow Dienst Anwendung** aus.  
  
2. Benennen Sie das neue Projekt, `ContractFirst` und klicken Sie auf **OK**.  
  
### <a name="creating-the-service-contract"></a>Erstellen des Dienstvertrags  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen**, **Neues Element** aus. Wählen Sie den **Code** Knoten auf der linken Seite und die **Klassen** Vorlage auf der rechten Seite aus. Benennen Sie die neue Klasse, `IBookService` und klicken Sie auf **OK**.  
  
2. Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. Erstellen Sie das Projekt, indem Sie **STRG + UMSCHALT + B** drücken.  
  
### <a name="importing-the-service-contract"></a>Importieren des Dienstvertrags  
  
1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstvertrag importieren**. **\<Current Project>** Öffnen Sie unter alle untergeordneten Knoten, und wählen Sie **ibookservice** aus. Klicken Sie auf **OK**.  
  
2. Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben. Klicken Sie auf **OK**.  
  
3. Erstellen Sie das Projekt, indem Sie **STRG + UMSCHALT + B** drücken, damit die importierten Aktivitäten in der Toolbox angezeigt werden.  
  
4. Öffnen Sie in **Projektmappen-Explorer** die Datei Service1. xamlx. Der Workflowdienst wird im Designer angezeigt.  
  
5. Wählen Sie die **Sequence** -Aktivität aus. Klicken Sie im Eigenschaftenfenster auf die **...** -Schaltfläche in der **implementedContract** -Eigenschaft. Klicken Sie im angezeigten Fenster typauflistungs- **Editor** auf die Dropdown Liste **Typ** , und wählen Sie die Option **Typen suchen...** . Öffnen Sie im Dialogfeld **.NET-Typ suchen und auswählen** unter **\<Current Project>** alle untergeordneten Knoten, und wählen Sie **ibookservice** aus. Klicken Sie auf **OK**. Klicken Sie im Dialogfeld typauflistungs- **Editor** auf **OK**.  
  
6. Wählen Sie die Aktivitäten **ReceiveRequest** und **SendResponse** aus, und löschen Sie Sie.  
  
7. Ziehen Sie aus der Toolbox eine **Buy_ReceiveAndSendReply** und eine **Checkout_Receive** -Aktivität auf die Aktivität **sequenzieller Dienst** .
