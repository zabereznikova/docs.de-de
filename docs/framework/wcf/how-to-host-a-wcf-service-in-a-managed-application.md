---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung'
description: Erfahren Sie, wie Sie einen WCF-Dienst in einer verwalteten Anwendung hosten, indem Sie einen selbst gehosteten Dienst erstellen und testen.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246167"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten App

Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.

Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf, um den Empfang von Nachrichten zu starten. Damit wird ein Listener für den Dienst erstellt und geöffnet Diese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt. Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz auf.

Ein Dienst kann auch in einem verwalteten Windows-Dienst in Internetinformationsdienste (IIS) oder in Windows Process Activation Service (WAS) gehostet werden. Weitere Informationen zu [Hostingoptionen](hosting-services.md)für einen Dienst finden Sie unter Hosting-Dienste.

Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Weitere Informationen zum Hosting von Diensten in verwalteten Anwendungen finden Sie unter [Hosting in einer verwalteten Anwendung](./feature-details/hosting-in-a-managed-application.md).

Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.

## <a name="create-a-self-hosted-service"></a>Erstellen eines selbst gehosteten Dienstanbieter

1. Erstellen Sie eine neue Konsolenanwendung:

   1. Öffnen Sie Visual Studio, **New**und wählen Sie  >  im Menü **Datei** die Option neues**Projekt** aus.

   2. Wählen Sie in der Liste **installierte Vorlagen** die Option **Visual c#** oder **Visual Basic**aus, und wählen Sie dann **Windows-Desktop**aus.

   3. Wählen Sie die **Konsolen-App** -Vorlage aus. Geben `SelfHost` Sie in das Feld **Name** ein, und **Klicken**Sie dann auf OK.

2. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf **SelfHost** , und wählen Sie **Verweis hinzufügen** Wählen Sie **System. Service Model** auf der Registerkarte **.net** aus, und klicken Sie dann auf **OK**.

    > [!TIP]
    > Wenn das **Projektmappen-Explorer** Fenster nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer** aus.

3. Doppelklicken Sie in **Projektmappen-Explorer** auf **Program.cs** oder **Module1. vb** , um die Datei im Code Fenster zu öffnen, wenn Sie nicht bereits geöffnet ist. Fügen Sie am Anfang der Datei die folgenden-Anweisungen ein:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Definieren und implementieren Sie einen Dienstvertrag. In diesem Beispiel wird ein `HelloWorldService`-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Weitere Informationen zum Definieren und Implementieren einer Dienst Schnittstelle finden Sie unter Gewusst [wie: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md) und Gewusst [wie: Implementieren eines Dienstvertrags](how-to-implement-a-wcf-contract.md).

5. Erstellen Sie am Beginn der `Main`-Methode eine Instanz der <xref:System.Uri>-Klasse mit der Basisadresse des Diensts.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse, wobei Sie ein <xref:System.Type>-Objekt, das den Diensttyp darstellt, und den URI (Uniform Resource Identifier) der Basisadresse <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben. Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode für das <xref:System.ServiceModel.ServiceHost>-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich. Wenn keine Endpunkte konfiguriert sind, wird von der Laufzeit ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird. Weitere Informationen zu Standard Endpunkten finden Sie unter [vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](./samples/simplified-configuration-for-wcf-services.md).

7. Drücken Sie **STRG** + **UMSCHALT** + **B** , um die Projekt Mappe zu erstellen.

## <a name="test-the-service"></a>Testen des Diensts

1. Drücken Sie **STRG** + **F5** , um den Dienst auszuführen.

2. Öffnen Sie den **WCF-Test Client**.

    > [!TIP]
    > Öffnen Sie zum Öffnen des **WCF-Test Clients**Developer-Eingabeaufforderung für Visual Studio, und führen Sie **WcfTestClient.exe**aus.

3. Wählen Sie im Menü **Datei** die Option **Dienst hinzufügen** aus.

4. Geben `http://localhost:8080/hello` Sie in das Feld Adresse ein, und klicken Sie auf **OK**.

    > [!TIP]
    > Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf. Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.

5. Doppelklicken Sie unter dem Knoten **meine Dienstprojekte** auf " **sayHello** ". Geben Sie den Namen in die Spalte **Wert** in der Liste **Anforderung** ein, und klicken Sie auf **aufrufen**.

   In der **Antwort** Liste wird eine Antwortnachricht angezeigt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode der <xref:System.ServiceModel.ServiceHost>-Instanz aufgerufen. Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Selbst gehostete Dienste](./samples/self-host.md)
- [Hosting-Dienste](hosting-services.md)
- [Vorgehensweise: Definieren eines Dienstvertrags](how-to-define-a-wcf-service-contract.md)
- [Vorgehensweise: Implementieren eines WCF-Dienstvertrags](how-to-implement-a-wcf-contract.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
- [Vom System bereitgestellte Bindungen](system-provided-bindings.md)
