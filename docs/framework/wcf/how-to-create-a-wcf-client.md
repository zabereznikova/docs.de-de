---
title: 'Gewusst wie: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 962f1255f3c759d623850678005eff138353cc80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Gewusst wie: Erstellen eines Windows Communication Foundation-Clients
Dies ist die vierte von sechs Aufgaben, die erforderlich sind, um einen Windows Communication Foundation (WCF)-Anwendung zu erstellen. Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.  
  
 In diesem Thema wird beschrieben, wie Metadaten von einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst abgerufen und dafür verwendet werden können, einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Clientproxy zu erstellen, der auf den Dienst zugreifen kann. Für diese Aufgabe wird die Funktion Dienstverweis hinzufügen verwendet, die von Visual Studio bereitgestellt wird. Dieses Tool ruft die Metadaten vom MEX-Endpunkt des Diensts ab und generiert eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen ausgewählten Sprache (standardmäßig C#). Zusätzlich zu dem Clientproxy erstellt oder aktualisiert das Tool die Clientkonfigurationsdatei, die es der Clientanwendung ermöglicht, über einen ihrer Endpunkte eine Verbindung mit dem Dienst herzustellen.  
  
> [!NOTE]
>  Sie können auch die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool, um die Proxyklasse und die Konfiguration anstelle von Hinzufügen eines Dienstverweises in Visual Studio generieren.  
  
> [!WARNING]
>  Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst aus einem Klassenbibliotheksprojekt in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] aufrufen, können Sie die Funktion zum Hinzufügen eines Dienstverweises verwenden, um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren.  Die Konfigurationsdatei wird nicht vom Klassenbibliotheksprojekt verwendet. Sie müssen der Datei app.config für die ausführbare Datei, die die Klassenbibliothek aufruft, die Einstellungen in der generierten Konfigurationsdatei hinzufügen.  
  
 Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Hierin wird beschrieben, [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>So erstellen Sie einen Windows Communication Foundation-Client  
  
1.  Erstellen Sie ein neues Konsolenanwendungsprojekt mit der rechten Maustaste auf die erste Schritte-Projektmappe, wenn Sie auswählen, **hinzufügen**, **neues Projekt**. In der **neues Projekt hinzufügen** -Dialogfeld auf der linken Seite der Dialogfeld Select **Windows** unter **c#** oder **VB**. Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung**. Benennen Sie das Projekt mit `GettingStartedClient`.  
  
2.  Legen Sie das Zielframework des GettingStartedClient-Projekts auf .NET Framework 4.5 per Rechtsklick auf **"gettingstartedclient"** im Projektmappen-Explorer auswählen und **Eigenschaften**. Im Dropdownfeld mit der Bezeichnung **Zielframework** wählen **.NET Framework 4.5**. Festlegen des Zielframeworks für ein VB-Projekt weicht etwas im Eigenschaftendialogfeld GettingStartedClient-Projekts klicken Sie auf die **Kompilieren** Registerkarte auf der linken Seite des Bildschirms, und klicken Sie dann auf die **erweitert Kompilieren Sie die Optionen** Schaltfläche auf der unteren linken Ecke des Dialogfelds. Wählen Sie dann **.NET Framework 4.5** im Dropdownfeld mit der Bezeichnung **Zielframework**.  
  
     Festlegen des Zielframeworks führt dazu, dass Visual Studio 2011, laden Sie die Projektmappe erneut drücken **OK** Aufforderung.  
  
3.  Fügen Sie einen Verweis auf System.ServiceModel auf das Projekt "gettingstartedclient", indem Sie mit der rechten Maustaste die **Verweis** Ordner unter dem Projekt "gettingstartedclient" im Projektmappen-Explorer und wählen **hinzufügen** Verweis. In der **Verweis hinzufügen** Dialogfeld wählen **Framework** auf der linken Seite des Dialogfelds. Geben Sie im Textfeld Assemblys suchen`System.ServiceModel` ein. Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel**, klicken Sie auf die **hinzufügen** aus, und klicken Sie auf die **schließen** Schaltfläche. Speichern Sie die Projektmappe, indem Sie auf die **alle speichern** Schaltfläche unterhalb des Hauptmenüs.  
  
4.  Als Nächstes fügen Sie einen Dienstverweis auf den Rechnerdienst hinzu. Zuvor müssen Sie die GettingStartedHost-Konsolenanwendung starten. Nachdem der Host ausgeführt wird können den Ordner "Verweise" unter dem Projekt "gettingstartedclient" im Projektmappen-Explorer mit der rechten Maustaste und wählen Sie Dienstverweis hinzufügen, und geben in der folgenden URL in das Adressfeld ein, der das Dialogfeld "Dienstverweis hinzufügen": HYPERLINK "http://localhost:8000/ServiceModelSamples/Service" http://localhost:8000/ServiceModelSamples/Service , und klicken Sie auf die **Go** Schaltfläche. Anschließend wird im Listenfeld Dienste der CalculatorService angezeigt. Doppelklicken Sie auf CalculatorService, um den Dienst zu erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen. Lassen Sie den Standardnamespace unverändert ist, und klicken Sie auf die **OK** Schaltfläche.  
  
     Wenn Sie mit Visual Studio einen Verweis auf einen Dienst hinzufügen, wird im Projektmappen-Explorer unter dem GettingStartedClient-Projekt unter dem Ordner Dienstverweise ein neuer Eintrag angezeigt.  Bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool eine Quellcodedatei und die Datei "App.config" generiert werden.  
  
     Sie können auch das Befehlszeilentool [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der entsprechenden Switches, um den Clientcode zu erstellen. Im folgenden Beispiel werden eine Code- und eine Konfigurationsdatei für den Dienst erstellt: Im ersten Beispiel wird gezeigt, wie Sie den Proxy in VB generieren, und im zweiten Beispiel wird gezeigt, wie Sie den Proxy in C# generieren:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 Sie haben jetzt den Proxy erstellt, über den die Clientanwendung den Rechnerdienst aufruft. Fahren Sie mit dem nächsten Thema in der Reihe: [Vorgehensweise: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
