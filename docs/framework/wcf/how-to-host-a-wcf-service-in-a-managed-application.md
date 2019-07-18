---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: b6d1c9c38e2cc5f1b1b7b5538af0339987563de6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637581"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten app

Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.

Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf, um den Empfang von Nachrichten zu starten. Damit wird ein Listener für den Dienst erstellt und geöffnet Diese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt. Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf.

Ein Dienst kann auch in einem verwalteten Windows-Dienst in Internetinformationsdienste (IIS) oder in Windows Process Activation Service (WAS) gehostet werden. Weitere Informationen zu den Hostoptionen für einen Dienst, finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).

Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Weitere Informationen zum Hosten von Diensten in verwalteten Anwendungen finden Sie unter [Hosten in einer verwalteten Anwendung](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).

Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.

## <a name="create-a-self-hosted-service"></a>Erstellen Sie einen selbst gehosteten Dienst

1. Erstellen Sie eine neue Konsolenanwendung:

   1. Öffnen Sie Visual Studio, und wählen Sie **neu** > **Projekt** aus der **Datei** Menü.

   2. In der **installierte Vorlagen** Liste **Visual C#-** oder **Visual Basic**, und wählen Sie dann **Windows Desktop**.

   3. Wählen Sie die **Konsolen-App** Vorlage. Typ `SelfHost` in die **Namen** Feld, und wählen Sie dann **OK**.

2. Mit der rechten Maustaste **SelfHost** in **Projektmappen-Explorer** , und wählen Sie **Verweis hinzufügen**. Wählen Sie **System.ServiceModel** aus der **.NET** Registerkarte, und wählen Sie dann **OK**.

    > [!TIP]
    > Wenn die **Projektmappen-Explorer** Fenster ist nicht sichtbar ist, wählen **Projektmappen-Explorer** aus der **Ansicht** Menü.

3. Doppelklicken Sie auf **"Program.cs"** oder **"Module1.vb"** in **Projektmappen-Explorer** , die sie im Codefenster zu öffnen, wenn es nicht bereits geöffnet ist. Fügen Sie die folgenden Anweisungen am Anfang der Datei hinzu:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Definieren und implementieren Sie einen Dienstvertrag. In diesem Beispiel wird ein `HelloWorldService`-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Weitere Informationen zum Definieren und Implementieren einer Dienstschnittstelle finden Sie unter [Vorgehensweise: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) und [Vorgehensweise: Implementieren ein Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).

5. Erstellen Sie am Beginn der `Main`-Methode eine Instanz der <xref:System.Uri>-Klasse mit der Basisadresse des Diensts.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse, wobei Sie ein <xref:System.Type>-Objekt, das den Diensttyp darstellt, und den URI (Uniform Resource Identifier) der Basisadresse <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben. Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.ServiceHost>-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich. Wenn keine Endpunkte konfiguriert sind, wird von der Laufzeit ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird. Weitere Informationen zu Standardendpunkten, finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

7. Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen der Projektmappe.

## <a name="test-the-service"></a>Testen des Diensts

1. Drücken Sie **STRG**+**F5** zum Ausführen des Diensts.

2. Open **WCF-Testclient**.

    > [!TIP]
    > Zum Öffnen **WCF-Testclient**, öffnen Sie die Developer-Eingabeaufforderung für Visual Studio, und führen Sie **WcfTestClient.exe**.

3. Wählen Sie **Dienst hinzufügen** aus der **Datei** Menü.

4. Typ `http://localhost:8080/hello` in das Feld Adresse ein, und klicken Sie auf **OK**.

    > [!TIP]
    > Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf. Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.

5. Doppelklicken Sie auf **SayHello** unter der **Meine Dienstprojekte** Knoten. Geben Sie Ihren Namen in der **Wert** -Spalte in der **anfordern** aus, und klicken Sie auf **Invoke**.

   Eine Reply-Nachricht wird angezeigt, der **Antwort** Liste.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz aufgerufen. Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
- [Hosting-Dienste](../../../docs/framework/wcf/hosting-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Vorgehensweise: Implementieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md)
