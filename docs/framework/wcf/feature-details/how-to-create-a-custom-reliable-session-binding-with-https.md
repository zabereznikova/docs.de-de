---
title: "Vorgehensweise: Erstellen einer benutzerdefinierten zuverl&#228;ssigen Sitzungsbindung mit HTTPS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Erstellen einer benutzerdefinierten zuverl&#228;ssigen Sitzungsbindung mit HTTPS
Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer \(SSL\)\-Transportsicherheit mit zuverlässigen Sitzungen.  Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS\-Transport verwendet.  Die zuverlässige Sitzung kann entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei aktiviert werden.  Diese Vorgehensweise verwendet die Konfigurationsdateien von Client und Dienst, um die zuverlässige Sitzung und das [\<httpsTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md)\-Element zu aktivieren.  
  
 Der wesentliche Teil dieser Prozedur ist der, dass das `endpoint`\-Konfigurationselement ein `bindingConfiguration`\-Attribut enthält, das auf eine benutzerdefinierte Bindungskonfiguration mit dem Namen "reliableSessionOverHttps" verweist.  Das [\<Bindung\>](../../../../docs/framework/misc/binding.md)`reliableSession-Konfigurationselement kann dann diesen Namen referenzieren, um festzulegen, dass eine zuverlässige Sitzung und der HTTPS-Transport verwendet werden, indem es die Elemente` `httpsTransport und`  einfügt.  
  
 Die Quellkopie dieses Beispiels finden Sie unter [Benutzerdefiniertes Binden von zuverlässigen Sitzungen über HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).  
  
### So konfigurieren Sie den Dienst mit 'CustomBinding' zur Verwendung einer zuverlässigen Sitzung mit HTTPS  
  
1.  Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]  
  
2.  Implementieren Sie den Dienstvertrag in einer Dienstklasse.  Beachten Sie, dass die Adresse oder die Bindungsinformationen in der Implementierung des Diensts nicht angegeben werden.  Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]  
  
3.  Erstellen Sie eine Web.config\-Datei, um einen Endpunkt für `CalculatorService` mit einer benutzerdefinierten Bindung namens "reliableSessionOverHttps" zu konfigurieren, die eine zuverlässige Sitzung und HTTPS\-Transport verwendet.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]  -->  
  
4.  Erstellen Sie eine Service.svc\-Datei, die die folgende Zeile enthält:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Stellen Sie die Datei Service.svc in das virtuelle IIS\-Verzeichnis.  
  
### So konfigurieren Sie den Client mit 'CustomBinding' zur Verwendung einer zuverlässigen Sitzung mit HTTPS  
  
1.  Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Befehlszeile, um Code aus Dienstmetadaten zu generieren.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Der generierte Client enthält die `ICalculator`\-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]  
  
3.  Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.  Beachten Sie, dass die Adresse und die Bindungsinformationen in der Implementierung des Diensts nirgendwo angegeben werden.  Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]  
  
4.  Konfigurieren Sie eine benutzerdefinierte Bindung mit dem Namen "reliableSessionOverHttps", um den HTTPS\-Transport und zuverlässige Sitzungen zu verwenden.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]  -->  
  
5.  Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]  
  
6.  Kompilieren Sie den Code, und führen Sie den Client aus.  
  
## Beispiel  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## .NET Framework-Sicherheit  
 Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, in Ihrem Browser auf eine HTTPS\-Adresse wie https:\/\/localhost\/servicemodelsamples\/service.svc zuzugreifen.  
  
## Siehe auch  
 [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)