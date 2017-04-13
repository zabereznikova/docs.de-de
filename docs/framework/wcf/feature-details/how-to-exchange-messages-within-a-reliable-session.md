---
title: "Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverl&#228;ssigen Sitzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverl&#228;ssigen Sitzung
Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, dies jedoch nicht standardmäßig.Die zuverlässige Sitzung kann entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei aktiviert werden.In dieser Prozedur werden die Client\- und die Dienstkonfigurationsdatei verwendet, um die zuverlässige Sitzung zu aktivieren und um festzulegen, dass die Nachrichten in der Reihenfolge empfangen werden, in der sie gesendet wurden.  
  
 Der wesentliche Teil dieser Prozedur ist der, dass das Element zur Endpunktkonfiguration ein `bindingConfiguration`\-Attribut enthält, das auf eine Bindungskonfiguration mit dem Namen "Binding1" verweist. Das [\<Bindung\>](../../../../docs/framework/misc/binding.md)`enabled-Konfigurationselement kann dann zum Aktivieren zuverlässiger Sitzungen auf diesen Namen verweisen, indem es das` [reliableSession\-Attribut des](http://msdn.microsoft.com/de-de/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)`true-Elements auf`  festlegt.Sie geben die Zusicherung einer Zustellung in der richtigen Reihenfolge für die zuverlässige Sitzung an, indem Sie das `ordered`\-Attribut auf `true` festlegen.  
  
 Die Quellkopie dieses Beispiels finden Sie unter [Zuverlässige WS\-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).  
  
### So konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung  
  
1.  Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]  
  
2.  Implementieren Sie den Dienstvertrag in einer Dienstklasse.Beachten Sie, dass die Adresse oder die Bindungsinformationen in der Implementierung des Diensts nicht angegeben werden.Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]  
  
3.  Erstellen Sie eine Web.config\-Datei, um einen Endpunkt für `CalculatorService` zu konfigurieren, der <xref:System.ServiceModel.WSHttpBinding> mit aktivierter zuverlässiger Sitzung und erforderlicher Zustellung der Nachrichten in der richtigen Reihenfolge verwendet.  
  
     [!code[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]  
  
4.  Erstellen Sie eine Datei Service.svc, die die folgende Zeile enthält:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Stellen Sie die Service.svc\-Datei in das virtuelle IIS\-Verzeichnis.  
  
### So konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung  
  
1.  Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Befehlszeile, um Code von Dienstmetadaten zu generieren:  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Der generierte Client enthält die `ICalculator`\-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]  
  
3.  Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.Beachten Sie, dass die Adresse und die Bindungsinformationen in der Implementierung des Diensts nirgendwo angegeben werden.Ebenso wenig muss Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]  
  
4.  Svcutil.exe generiert auch die Konfiguration für den Client, der die <xref:System.ServiceModel.WSHttpBinding>\-Klasse verwendet.Diese Datei muss bei Verwendung von [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] App.config genannt werden.  
  
     [!code[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]  
  
5.  Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]  
  
6.  Kompilieren Sie den Code, und führen Sie den Client aus.  
  
## Beispiel  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 Mehrere der vom System bereitgestellten Bindungen unterstützen standardmäßig zuverlässige Sitzungen.Dazu gehören:  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
  
 Ein Beispiel zum Erstellen einer benutzerdefinierten Bindung, die zuverlässige Sitzungen unterstützt, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).  
  
## Siehe auch  
 [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)