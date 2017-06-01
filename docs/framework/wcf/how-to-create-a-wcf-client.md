---
title: "Vorgehensweise: Erstellen eines Windows Communication Foundation-Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Clients [WCF], Ausführen"
  - "WCF-Clients [WCF], Ausführen"
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
caps.latest.revision: 64
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 64
---
# Vorgehensweise: Erstellen eines Windows Communication Foundation-Clients
Dies ist die vierte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendung erforderlich sind.Eine Übersicht über alle sechs Aufgaben finden Sie im Thema [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 In diesem Thema wird beschrieben, wie Metadaten von einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst abgerufen und dafür verwendet werden können, einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxy zu erstellen, der auf den Dienst zugreifen kann.Diese Aufgabe wird ausgeführt, indem die Funktion "Dienstverweis hinzufügen" von Visual Studio verwendet wird.Dieses Tool ruft die Metadaten vom MEX\-Endpunkt des Diensts ab und generiert eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen ausgewählten Sprache \(standardmäßig C\#\).Zusätzlich zu dem Clientproxy erstellt oder aktualisiert das Tool auch eine Konfigurationsdatei für den Client, die es der Clientanwendung ermöglicht, über einen ihrer Endpunkte eine Verbindung mit dem Dienst herzustellen.  
  
> [!NOTE]
>  Sie können auch das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\-Tool verwenden, um die Proxyklasse und Konfiguration anstelle der Visual Studio\-Funktion "Dienstverweis hinzufügen" zu verwenden.  
  
> [!WARNING]
>  Wenn Sie einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst aus einem Klassenbibliotheksprojekt in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] aufrufen, können Sie die Funktion zum Hinzufügen eines Dienstverweises verwenden, um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren.Die Konfigurationsdatei wird nicht vom Klassenbibliotheksprojekt verwendet.Sie müssen die Einstellungen in der generierten Konfigurationsdatei der Datei app.config für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.  
  
 Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren.Dieses Verfahren wird unter [Gewusst wie: Verwenden eines Clients](../../../docs/framework/wcf/how-to-use-a-wcf-client.md) beschrieben.  
  
### So erstellen Sie einen Windows Communication Foundation\-Client  
  
1.  Erstellen Sie ein neues Konsolenanwendungsprojekt, indem Sie mit der rechten Maustaste auf die Projektmappe "Erste Schritte" klicken und dann **Hinzufügen** und **Neues Projekt** auswählen.Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** auf der linken Seite des Dialogfelds **Windows** unter **C\#** oder **VB** aus.Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung** aus.Geben Sie dem Projekt den Namen `GettingStartedClient`.  
  
2.  Legen Sie das Zielframework des GettingStartedClient\-Projekts auf .NET Framework 4.5 fest, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **GettingStartedClient** klicken und **Eigenschaften** auswählen.Wählen Sie im Dropdownfeld **Zielframework** den Eintrag **.NET Framework 4.5** aus.Das Festlegen des Zielframeworks für ein VB\-Projekt weicht etwas davon ab. Klicken Sie im Eigenschaftendialogfeld des GettingStartedClient\-Projekts links im Bildschirm auf die Registerkarte **Kompilieren**, und klicken Sie dann unten links im Dialogfeld auf die Schaltfläche **Erweiterte Kompilierungsoptionen**.Wählen Sie im Dropdownfeld **Zielframework**den Eintrag **.NET Framework** aus.  
  
     Das Festlegen des Zielframeworks führt dazu, dass die Projektmappe von Visual Studio 2011 neu geladen wird. Klicken Sie auf **OK**, wenn Sie dazu aufgefordert werden.  
  
3.  Fügen Sie dem GettingStartedClient\-Projekt einen Verweis auf System.ServiceModel hinzu, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Ordner **Verweis** unter dem GettingStartedClient\-Projekt klicken, und wählen Sie **Verweis hinzufügen** aus.Wählen Sie im Dialogfeld **Verweis hinzufügen** links im Dialogfeld **Framework** aus.Geben Sie im Textfeld **Assemblys suchen**`System.ServiceModel` ein.Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel** aus, und klicken Sie auf die Schaltfläche **Hinzufügen** und auf die Schaltfläche **Schließen**.Speichern Sie die Projektmappe, indem Sie unterhalb des Hauptmenüs auf die Schaltfläche **Alle speichern** klicken.  
  
4.  Als Nächstes fügen Sie einen Dienstverweis auf den Rechnerdienst hinzu.Zuvor müssen Sie die GettingStartedHost\-Konsolenanwendung starten.Sobald der Host ausgeführt wird, können Sie mit der rechten Maustaste auf den Ordner **Verweise** unter dem GettingStartedClient\-Projekt im Projektmappen\-Explorer klicken und **Dienstverweis hinzufügen** auswählen. Geben Sie dann die folgende URL in das Adressfeld des Dialogfelds **Dienstverweis hinzufügen** ein: http:\/\/localhost:8000\/ServiceModelSamples\/Service, und klicken Sie auf die Schaltfläche **Gehe zu**.Der CalculatorService sollte daraufhin im Listenfeld **Dienste** angezeigt werden. Doppelklicken Sie auf CalculatorService, um den Dienst zu erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen.Lassen Sie den Standardnamespace unverändert, und klicken Sie auf die Schaltfläche **OK**.  
  
     Wenn Sie einen Verweis auf ein Dienst mit Visual Studio hinzufügen, wird im Projektmappen\-Explorer unter dem Ordner **Dienstverweise** unter dem GettingStartedClient\-Projekt ein neuer Eintrag angezeigt.Wenn Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)\-Tool verwenden, werden eine Quellcodedatei und eine app.config\-Datei generiert.  
  
     Sie können auch das Befehlszeilentool [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit den entsprechenden Schaltern verwenden, um den Clientcode zu erstellen.Im folgenden Beispiel werden eine Code\- und eine Konfigurationsdatei für den Dienst erstellt:Im ersten Beispiel wird gezeigt, wie Sie den Proxy in VB generieren, und im zweiten Beispiel wird gezeigt, wie Sie den Proxy in C\# generieren:  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
  
    ```  
  
 Sie haben jetzt den Proxy erstellt, über den die Clientanwendung den Rechnerdienst aufruft.Wechseln Sie zum nächsten Thema in der Reihe: [Gewusst wie: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## Siehe auch  
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)