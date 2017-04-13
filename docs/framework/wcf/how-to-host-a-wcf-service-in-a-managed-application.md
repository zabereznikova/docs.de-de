---
title: "Gewusst wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung | Microsoft Docs"
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
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# Gewusst wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung
Wenn ein Dienst in einer verwalteten Anwendung gehostet werden soll, betten Sie den Code für den Dienst in den verwalteten Anwendungscode ein, definieren Sie entweder imperativ im Code, deklarativ über die Konfiguration oder mithilfe der Standardendpunkte einen Endpunkt für den Dienst, und erstellen Sie dann eine Instanz von <xref:System.ServiceModel.ServiceHost>.  
  
 Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>\-Methode der <xref:System.ServiceModel.ServiceHost>\-Instanz auf, um den Empfang von Nachrichten zu starten.Damit wird ein Listener für den Dienst erstellt und geöffnetDiese Art des Hostings wird häufig auch als "Selbsthosting" bezeichnet, weil die verwaltete Anwendung selbst die für das Hosting erforderlichen Vorgänge ausführt.Um den Dienst zu schließen, rufen Sie die <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName>\-Methode der <xref:System.ServiceModel.ServiceHost>\-Instanz auf.  
  
 Ein Dienst kann auch in einem verwalteten Windows\-Dienst in Internet Information Services \(IIS\) oder in Windows Process Activation Service \(WAS\) gehostet werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu den Hostoptionen für einen Dienst finden Sie unter [Hosting\-Dienste](../../../docs/framework/wcf/hosting-services.md).  
  
 Dienste in einer verwalteten Anwendung zu hosten ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Hosting von Diensten in verwalteten Anwendungen finden Sie unter [Hosten in einer verwalteten Anwendung](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
 Im folgenden Verfahren wird das Implementieren eines selbst gehosteten Diensts in einer Konsolenanwendung veranschaulicht.  
  
### So erstellen Sie einen selbst gehosteten Dienst  
  
1.  Klicken Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], und wählen Sie im Menü **Datei** zunächst **Neu** und dann **Projekt...** aus.  
  
2.  Wählen Sie in der Liste **Installierte Vorlagen** die Option **Visual C\#** und anschließend **Windows** oder **Visual Basic** aus.Abhängig von den [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]\-Einstellungen befindet sich ggf. eine oder es befinden sich beide Optionen im Knoten **Andere Sprachen** in der Liste **Installierte Vorlagen**.  
  
3.  Wählen Sie in der Liste **Windows** die Option **Konsolenanwendung** aus.Geben Sie im Feld **Name** die Bezeichnung `SelfHost` ein, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **SelfHost**, und wählen Sie **Verweis hinzufügen** aus.Wählen Sie auf der Registerkarte **.NET** die Option **System.ServiceModel** aus, und klicken Sie anschließend auf **OK**.  
  
    > [!TIP]
    >  Wenn das Fenster **Projektmappen\-Explorer** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Projektmappen\-Explorer** aus.  
  
5.  Doppelklicken Sie im Fenster von **Projektmappen\-Explorer** auf die Datei **Program.cs** oder **Module1.vb**, um sie ggf. im Codefenster zu öffnen.Fügen Sie am Anfang der Datei die folgenden Anweisungen ein.  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  Definieren und implementieren Sie einen Dienstvertrag.In diesem Beispiel wird ein `HelloWorldService`\-Element definiert, das auf Grundlage der Eingabe in den Dienst eine Nachricht zurückgibt.  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Definieren und Implementieren einer Dienstschnittstelle finden Sie unter [Gewusst wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) und [Gewusst wie: Implementieren eines WCF\-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).  
  
7.  Erstellen Sie am Beginn der `Main`\-Methode eine Instanz der <xref:System.Uri>\-Klasse mit der Basisadresse des Diensts.  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>\-Klasse, wobei Sie ein <xref:System.Type>\-Objekt, das den Diensttyp darstellt, und den URI \(Uniform Resource Identifier\) der Basisadresse [ServiceHost\(Type, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> übergeben.Aktivieren Sie die Veröffentlichung von Metadaten, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>\-Methode für das <xref:System.ServiceModel.ServiceHost>\-Objekt auf, um den Dienst zu initialisieren und auf den Empfang von Nachrichten vorzubereiten.  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]  
  
    > [!NOTE]
    >  In diesem Beispiel werden Standardendpunkte verwendet. Für diesen Dienst ist keine Konfigurationsdatei erforderlich.Wenn keine Endpunkte konfiguriert sind, wird von der Runtime ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag hinzugefügt, der vom Dienst implementiert wird.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten finden Sie unter [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
### So testen Sie den Dienst  
  
1.  Drücken Sie STRG\+F5, um den Dienst auszuführen.  
  
2.  Öffnen Sie den **WCF\-Testclient**.  
  
    > [!TIP]
    >  Zum Starten von **WCF\-Testclient** öffnen Sie die [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]\-Eingabeaufforderung und geben **WcfTestClient.exe** ein.  
  
3.  Wählen Sie im Menü **Datei** den Befehl **Dienst hinzufügen** aus.  
  
4.  Geben Sie im Adressfeld die Bezeichnung `http://localhost:8080/hello` ein, und klicken Sie auf **OK**.  
  
    > [!TIP]
    >  Stellen Sie sicher, dass der Dienst ausgeführt wird, oder ein Fehler tritt bei diesem Schritt auf.Haben Sie die Basisadresse im Code geändert, verwenden Sie in diesem Schritt die geänderte Basisadresse.  
  
5.  Doppelklicken Sie im Knoten **Meine Dienstprojekte** auf **SayHello**.Geben Sie in der Liste **Anforderung** in der Spalte **Wert** Ihren Namen ein, und klicken Sie auf **Aufrufen**.In der Liste **Antwort** erscheint nun eine Antwortnachricht.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.ServiceModel.ServiceHost>\-Objekt als Host für einen Dienst des Typs `HelloWorldService` erstellt, und dann wird die <xref:System.ServiceModel.ICommunicationObject.Open%2A>\-Methode der <xref:System.ServiceModel.ServiceHost>\-Instanz aufgerufen.Im Code wird eine Basisadresse bereitgestellt, die Metadatenveröffentlichung ist aktiviert, und Standardendpunkte werden verwendet.  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## Siehe auch  
 <xref:System.Uri>   
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>   
 <xref:System.Configuration.ConfigurationManager>   
 [Gewusst wie: Hosten eines WCF\-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)   
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)   
 [Hosting\-Dienste](../../../docs/framework/wcf/hosting-services.md)   
 [Gewusst wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)   
 [Gewusst wie: Implementieren eines WCF\-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md)