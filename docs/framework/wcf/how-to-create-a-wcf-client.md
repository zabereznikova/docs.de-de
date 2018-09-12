---
title: 'Gewusst wie: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 9e6d75bf8911a3c36e63b3bc108faae823434d1d
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44509998"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Gewusst wie: Erstellen eines Windows Communication Foundation-Clients

Dies ist die vierte von sechs Aufgaben, die zum Erstellen einer Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).

Dieses Thema beschreibt das Abrufen von Metadaten von einem WCF-Dienst aus, und verwenden, um einen WCF-Proxy zu erstellen, der den Dienst zugreifen können. Für diese Aufgabe wird die Funktion Dienstverweis hinzufügen verwendet, die von Visual Studio bereitgestellt wird. Dieses Tool ruft die Metadaten vom MEX-Endpunkt des Diensts ab und generiert eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen ausgewählten Sprache (standardmäßig C#). Zusätzlich zu dem Clientproxy erstellt oder aktualisiert das Tool die Clientkonfigurationsdatei, die es der Clientanwendung ermöglicht, über einen ihrer Endpunkte eine Verbindung mit dem Dienst herzustellen.

> [!NOTE]
> Sie können auch die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool zum Generieren der Proxyklasse und Konfiguration anstelle von "Dienstverweis hinzufügen", in Visual Studio.

> [!WARNING]
> Beim Aufrufen eines WCF-Diensts aus einem Klassenbibliotheksprojekt in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] können Sie das Feature Dienstverweis hinzufügen um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren.  Die Konfigurationsdatei wird nicht vom Klassenbibliotheksprojekt verwendet. Sie müssen der Datei app.config für die ausführbare Datei, die die Klassenbibliothek aufruft, die Einstellungen in der generierten Konfigurationsdatei hinzufügen.

 Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Dieses Verfahren wird beschrieben, [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>So erstellen Sie einen Windows Communication Foundation-Client

1.  Erstellen Sie ein neues Konsolenanwendungsprojekt, indem Sie mit der rechten Maustaste auf die erste Schritte-Projektmappe, wenn Sie auswählen, **hinzufügen**, **neues Projekt**. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** auf der linken Seite des Dialogfelds unter **C#** oder **VB** die Option **Windows** aus. Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung** aus. Benennen Sie das Projekt mit `GettingStartedClient`.

2.  Legen Sie das Zielframework des GettingStartedClient-Projekts auf .NET Framework 4.5, indem Sie mit der rechten Maustaste auf **"gettingstartedclient"** im Projektmappen-Explorer und Auswählen von **Eigenschaften**. Wählen Sie im Dropdownfeld **Zielframework** **.NET Framework 4.5** aus. Klicken Sie mit der Festlegen des Zielframeworks für ein VB-Projekt weicht etwas im Eigenschaftendialogfeld GettingStartedClient-Projekt auf die **Kompilieren** auf der linken Seite des Bildschirms, und klicken Sie dann auf die **erweitert Kompilierungsoptionen** Schaltfläche in der unteren linken Ecke des Dialogfelds. Wählen Sie dann **.NET Framework 4.5** im Dropdownfeld **Zielframework** aus.

     Festlegen des Zielframeworks führt dazu, dass Visual Studio 2011 auf die Projektmappe erneut drücken Sie die **OK** Aufforderung.

3.  Fügen Sie einen Verweis auf den System.ServiceModel dem GettingStartedClient-Projekt, indem Sie mit der rechten Maustaste die **Verweis** Ordner unter dem GettingStartedClient-Projekt im Projektmappen-Explorer und wählen **hinzufügen** Verweis. Wählen Sie links im Dialogfeld **Verweis hinzufügen** **Framework** aus. Geben Sie im Textfeld Assemblys suchen`System.ServiceModel` ein. Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel** aus, klicken Sie auf die Schaltfläche **Hinzufügen** und dann auf die Schaltfläche **Schließen**. Speichern Sie die Projektmappe, indem Sie auf die **Alles speichern** Schaltfläche unterhalb des Hauptmenüs.

4.  Als Nächstes fügen Sie einen Dienstverweis auf den Rechnerdienst hinzu. Zuvor müssen Sie die GettingStartedHost-Konsolenanwendung starten. Sobald der Host ausgeführt wird, mit der rechten Maustaste die **Verweise** Ordner unter dem GettingStartedClient-Projekt in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**  >   **Dienstverweis**. Geben Sie die folgende URL in das Adressfeld des der **Hinzufügen eines Dienstverweises** Dialogfeld: [ http://localhost:8000/ServiceModelSamples/Service ](http://localhost:8000/ServiceModelSamples/Service) , und klicken Sie auf die **wechseln** Schaltfläche. Der CalculatorService sollte dann im Listenfeld Dienste angezeigt werden. Doppelklicken Sie auf CalculatorService und erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen. Lassen Sie den Standardnamespace unverändert ist, und klicken Sie auf die **OK** Schaltfläche.

     Wenn Sie mit Visual Studio einen Verweis auf einen Dienst hinzufügen, wird im Projektmappen-Explorer unter dem GettingStartedClient-Projekt unter dem Ordner Dienstverweise ein neuer Eintrag angezeigt.  Bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool eine Quellcodedatei und die Datei "App.config" generiert werden.

     Sie können auch das Befehlszeilentool [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit den entsprechenden Schaltern, um den Clientcode zu erstellen. Im folgenden Beispiel werden eine Code- und eine Konfigurationsdatei für den Dienst erstellt: Im ersten Beispiel wird gezeigt, wie Sie den Proxy in VB generieren, und im zweiten Beispiel wird gezeigt, wie Sie den Proxy in C# generieren:

    ```
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service
    ```

    ```csharp
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service
    ```

 Sie haben jetzt den Proxy erstellt, über den die Clientanwendung den Rechnerdienst aufruft. Mit dem nächsten Thema in der Reihe fortfahren: [Vorgehensweise: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>Siehe auch

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
