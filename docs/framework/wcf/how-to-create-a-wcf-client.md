---
title: 'Gewusst wie: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 1eadb5008575a1a53d685db14d68e42d0dce1360
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46478291"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>Gewusst wie: Erstellen eines Windows Communication Foundation-Clients

Dies ist die vierte von sechs Aufgaben, die zum Erstellen einer Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).

Dieses Thema beschreibt das Abrufen von Metadaten von einem WCF-Dienst aus, und verwenden, um einen WCF-Proxy zu erstellen, der den Dienst zugreifen können. Diese Aufgabe wird mithilfe der **Hinzufügen eines Dienstverweises** Funktionalität von Visual Studio. Dieses Tool ruft die Metadaten vom MEX-Endpunkt des Diensts ab und generiert eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen ausgewählten Sprache (standardmäßig C#). Zusätzlich zu dem Clientproxy erstellt oder aktualisiert das Tool die Clientkonfigurationsdatei, die es der Clientanwendung ermöglicht, über einen ihrer Endpunkte eine Verbindung mit dem Dienst herzustellen.

> [!NOTE]
> Sie können auch die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool zum Generieren der Proxyklasse und Konfiguration anstelle von **Hinzufügen eines Dienstverweises** in Visual Studio.

> [!NOTE]
> Beim Aufrufen eines WCF-Diensts aus einem Klassenbibliotheksprojekt in Visual Studio können Sie die **Hinzufügen eines Dienstverweises** Funktion, um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren. Die Konfigurationsdatei wird nicht vom Klassenbibliotheksprojekt verwendet. Sie müssen die Einstellungen in der generierten Konfigurationsdatei an der Datei "App.config" für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.

Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Dieses Verfahren wird beschrieben, [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="to-create-a-windows-communication-foundation-client"></a>So erstellen Sie einen Windows Communication Foundation-Client

1. Erstellen Sie ein neues Konsolenanwendungsprojekt in Visual Studio. Mit der rechten Maustaste auf die erste Schritte-Lösung im **Projektmappen-Explorer** , und wählen Sie **hinzufügen** > **neues Projekt**. In der **neues Projekt hinzufügen** im Dialogfeld auf der linken Seite, und wählen die **Windows Desktop** unter Kategorie **Visual C#-** oder **Visual Basic**. Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und nennen Sie das Projekt **"gettingstartedclient"**.

2. Fügen Sie dem GettingStartedClient-Projekt einen Verweis auf den System.ServiceModel hinzu. Mit der rechten Maustaste auf die **Verweise** Ordner unter dem GettingStartedClient-Projekt in **Projektmappen-Explorer**, und wählen Sie dann **Verweis hinzufügen**. In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Framework** auf der linken Seite des Dialogfelds unter **Assemblys**. Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**. Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.

3. Fügen Sie einen Dienstverweis auf den Rechnerdienst hinzu.

   1. Starten Sie die GettingStartedHost-Konsolenanwendung.

   2. Sobald der Host ausgeführt wird, mit der rechten Maustaste die **Verweise** Ordner unter dem GettingStartedClient-Projekt in **Projektmappen-Explorer** , und wählen Sie **hinzufügen**  >   **Dienstverweis**.

   3. Geben Sie die folgende URL in das Adressfeld ein, der die **Hinzufügen eines Dienstverweises** Dialogfeld: [http://localhost:8000/GettingStartedClient/Service](http://localhost:8000/GettingStartedClient/Service)

   4. Wählen Sie **wechseln**.

   Der CalculatorService wird angezeigt, der **Services** Listenfeld. Doppelklicken Sie auf der CalculatorService zum Erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen. Lassen Sie den Standardnamespace als-ist, und wählen Sie **OK**.

    Wenn Sie einen Verweis auf einen Dienst mithilfe von Visual Studio hinzufügen, ein neues Element erscheint **Projektmappen-Explorer** unter der **Dienstverweise** Ordner unter dem GettingStartedClient-Projekt. Bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool, eine Quellcodedatei und die Datei "App.config" generiert werden.

    Sie können auch das Befehlszeilentool [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit den entsprechenden Schaltern, um den Clientcode zu erstellen. Im folgenden Beispiel werden eine Code- und eine Konfigurationsdatei für den Dienst erstellt: Das erste Beispiel zeigt, wie Sie den Proxy in VB generieren, und die zweite zeigt, wie in c# den Proxy zu generieren:

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

## <a name="next-steps"></a>Nächste Schritte

Sie haben den Proxy erstellt, mit denen die Clientanwendung den rechnerdienst aufruft. Fahren Sie mit dem nächsten Thema in der Reihe.

> [!div class="nextstepaction"]
> [Vorgehensweise: Konfigurieren eines Clients](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>Siehe auch

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
