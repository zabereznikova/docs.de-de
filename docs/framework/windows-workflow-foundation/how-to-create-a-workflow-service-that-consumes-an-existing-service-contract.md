---
title: 'Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags'
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: c2ca9c349718c3939d74d052ff0ed448879cd045
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344714"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a>Vorgehensweise: Erstellen eines Workflowdiensts zum Verarbeiten eines vorhandenen Dienstvertrags
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] -Funktionen verbessern die Integration zwischen Webdiensten und Workflows in Form der Vertrag zuerst-Workflowentwicklung. Das Tool für die Vertrag zuerst-Workflowentwicklung ermöglicht es Ihnen, den Vertrag zuerst im Code zu entwerfen. Das Tool generiert dann automatisch eine Aktivitätsvorlage für die Vertragsvorgänge in der Toolbox.  
  
> [!NOTE]
>  Dieses Thema enthält eine schrittweise Anleitung zum Erstellen eines Vertrag zuerst-Workflowdiensts. Weitere Informationen zum Entwickeln von Vertrag zuerst-Workflowdiensten finden Sie unter [Workflow Entwickeln von Vertrag zuerst](contract-first-workflow-service-development.md).  
  
### <a name="creating-the-workflow-project"></a>Erstellen des Workflowprojekts  
  
1. Wählen Sie in Visual Studio **Datei**, **neues Projekt**. Wählen Sie die **WCF** unter den Knoten der **C#** Knoten in der **Vorlagen** Struktur, und wählen Sie die **WCF Workflow Service Application** Vorlage.  
  
2. Nennen Sie das neue Projekt `ContractFirst` , und klicken Sie auf **Ok**.  
  
### <a name="creating-the-service-contract"></a>Erstellen des Dienstvertrags  
  
1. Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und wählen Sie **hinzufügen**, **neues Element...** . Wählen Sie die **Code** Knoten auf der linken Seite, und die **Klasse** Vorlage auf der rechten Seite. Nennen Sie die neue Klasse `IBookService` , und klicken Sie auf **Ok**.  
  
2. Fügen Sie `System.Servicemodel` im oberen Bereich des angezeigten Codefensters eine Using-Anweisung hinzu.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. Ändern Sie die Beispielklassendefinition in die folgende Schnittstellendefinition.  
  
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
  
4. Erstellen Sie das Projekt durch Drücken von **STRG + UMSCHALT + B**.  
  
### <a name="importing-the-service-contract"></a>Importieren des Dienstvertrags  
  
1. Mit der rechten Maustaste in des Projekts im **Projektmappen-Explorer** , und wählen Sie **Dienstvertrag importieren**. Klicken Sie unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**. Klicken Sie auf **OK**.  
  
2. Es wird ein Dialogfeld mit dem Hinweis geöffnet, dass der Vorgang erfolgreich abgeschlossen wurde und dass die generierten Aktivitäten in der Toolbox angezeigt werden, nachdem Sie das Projekt erstellt haben. Klicken Sie auf **OK**.  
  
3. Erstellen Sie das Projekt durch Drücken von **STRG + UMSCHALT + B**, sodass die importierten Aktivitäten in der Toolbox angezeigt werden.  
  
4. In **Projektmappen-Explorer**, Service1.xamlx zu öffnen. Der Workflowdienst wird im Designer angezeigt.  
  
5. Wählen Sie die **Sequenz** Aktivität. Klicken Sie im Eigenschaftenfenster auf die **...** Schaltfläche der **ImplementedContract** Eigenschaft. In der **Typauflistungs-Editor** Fenster, das angezeigt wird, klicken Sie auf die **Typ** Dropdown-Liste, und wählen Sie die **nach Typen suchen...** Eintrag. In der **durchsuchen, und wählen Sie einen .NET-Typ** Dialogfeld unter  **\<aktuelles Projekt >**, öffnen Sie alle untergeordneten Knoten, und wählen Sie **IBookService**. Klicken Sie auf **OK**. In der **Typauflistungs-Editor** Dialogfeld klicken Sie auf **OK**.  
  
6. Wählen Sie aus, und löschen Sie die **ReceiveRequest** und **SendResponse** Aktivitäten.  
  
7. Ziehen Sie aus der Toolbox ein **Buy_ReceiveAndSendReply** und **Checkout_Receive** Aktivität auf die **sequenzieller Dienst** Aktivität.
