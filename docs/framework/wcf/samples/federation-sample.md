---
title: Verbundbeispiel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 58a8ab012682d5acb04b201c36d931276426ffe8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="federation-sample"></a>Verbundbeispiel
Dieses Beispiel veranschaulicht die Verbundsicherheit.  
  
## <a name="sample-details"></a>Beispieldetails  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bietet Unterstützung für die Bereitstellung von Verbundsicherheitsarchitekturen durch `wsFederationHttpBinding`. Die `wsFederationHttpBinding` bietet eine sichere, zuverlässige und interoperable Bindung, die die Verwendung von HTTP als den zugrunde liegenden Transportmechanismus für die Anforderungs-Antwort-Kommunikation umfasst, während Text und XML als Übertragungsformate für die Codierung verwendet werden. Weitere Informationen zu den Verbund in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], finden Sie unter [Verbund](../../../../docs/framework/wcf/feature-details/federation.md).  
  
 Das Szenario besteht aus 4 Einheiten:  
  
-   BookStore-Dienst  
  
-   BookStore STS  
  
-   HomeRealm STS  
  
-   BookStore-Client  
  
 Der BookStore-Dienst unterstützt zwei Vorgänge: `BrowseBooks` und `BuyBook`. Es lässt anonymen Zugriff auf den `BrowseBooks`-Vorgang zu, aber erfordert authentifizierten Zugriff, um auf den `BuyBooks`-Vorgang zuzugreifen. Die Authentifizierung hat das Format eines Tokens, das von BookStore STS ausgegeben wird. Die Konfigurationsdatei zum BookStore-Dienst verweist Clients mit `wsFederationHttpBinding` auf BookStore STS.  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 BookStore STS erfordert dann, dass Clients mit einem von HomeRealm STS ausgegebenen Token authentifiziert werden. Die Konfigurationsdatei für BookStore STS verweist dann Clients mit `wsFederationHttpBinding` auf HomeRealm STS.  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 Die Sequenz von Ereignissen beim Zugriff auf den `BuyBook`-Vorgang lautet wie folgt:  
  
1.  Der Client wird mit Windows-Anmeldeinformationen bei HomeRealm STS authentifiziert.  
  
2.  HomeRealm STS gibt ein Token aus, das verwendet werden kann, um bei BookStore STS authentifiziert zu werden.  
  
3.  Der Client wird bei BookStore STS mit einem von HomeRealm STS ausgegebenen Token authentifiziert.  
  
4.  BookStore STS gibt ein Token aus, das verwendet werden kann, um beim BookStore-Dienst authentifiziert zu werden.  
  
5.  Der Client wird beim BookStore-Dienst mit einem von BookStore STS ausgegebenen Token authentifiziert.  
  
6.  Der Client greift auf den `BuyBook`-Vorgang zu.  
  
 In den folgenden Anweisungen finden Sie Informationen zum Einrichten und Ausführen dieses Beispiels.  
  
> [!NOTE]
>  Sie benötigen Schreibzugriff auf die **"Wwwroot"** Verzeichnis zum Ausführen dieses Beispiels.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie das SDK-Befehlsfenster. Führen Sie im Beispielpfad die Datei "Setup.bat" aus. Dadurch werden die erforderlichen virtuellen Verzeichnisse für das Beispiel erstellt und die erforderlichen Zertifikate mit entsprechenden Berechtigungen installiert.  
  
    > [!NOTE]
    >  Die Batchdatei "Setup.bat" ist dafür ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden. Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt. Bei [!INCLUDE[wv](../../../../includes/wv-md.md)] müssen Sie sicherstellen, dass IIS 6.0-Verwaltungskompatibilität installiert ist, da das Setup die IIS-Administratorskripts verwendet. Das Ausführen des Setupskripts über [!INCLUDE[wv](../../../../includes/wv-md.md)] erfordert Administratorrechte.  
  
2.  Öffnen Sie die Datei FederationSample.sln in Visual Studio, und wählen Sie **Projektmappe** aus der **erstellen** Menü. Dadurch werden die allgemeinen Projektdateien, der Bookstore-Dienst, Bookstore-STS und HomeRealm STS erstellt und in IIS bereitgestellt. Auf diese Weise wird auch die Buchhandlungsclientanwendung erstellt, und die ausführbare Datei "BookStoreClient.exe" wird im Ordner "FederationSample\BookStoreClient\bin\Debug" gespeichert.  
  
3.  Doppelklicken Sie auf "BookStoreClient.exe". Das Fenster "BookStoreClient" wird angezeigt.  
  
4.  Sie können die in der Buchhandlung verfügbaren Bücher durchsuchen, indem Sie auf **Bücher Durchsuchen**.  
  
5.  Um ein bestimmtes Buch zu kaufen, wählen Sie das Buch in der Liste aus, und klicken Sie auf **Buch kaufen**. Die Anwendung startet und wird mit der Windows-Authentifizierung beim HomeRealm-Sicherheitstokendienst authentifiziert.  
  
     Das Beispiel ist so konfiguriert, dass Benutzern der Kauf von Büchern ermöglicht wird, die $15 oder weniger kosten. Wenn versucht wird, Bücher zu kaufen, die mehr als $15 kosten, erhält der Client vom BookStore-Dienst eine Nachricht vom Typ Zugriff verweigert.  
  
    > [!NOTE]
    >  Im Beispiel wird der Kreditrahmen des Benutzers nach einem Kauf nicht aktualisiert. Sie können immer wieder Bücher innerhalb des Kreditrahmens (fest) des Benutzers kaufen.  
  
#### <a name="to-clean-up"></a>So führen Sie eine Bereinigung durch  
  
1.  Führen Sie die Datei Cleanup.bat aus. Dadurch werden die virtuellen Verzeichnisse, die beim Setup erstellt wurden, gelöscht, und auch die beim Setup installierten Zertifikate werden entfernt.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a>Siehe auch
