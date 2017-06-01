---
title: "Vorgehensweise: Angeben von Anmeldeinformationen f&#252;r Kanalsicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
caps.latest.revision: 18
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 18
---
# Vorgehensweise: Angeben von Anmeldeinformationen f&#252;r Kanalsicherheit
Der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienstmoniker ermöglicht COM-Anwendungen das Aufrufen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten. Die meisten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste fordern vom Client die Angabe von Anmeldeinformationen für Authentifizierung und Autorisierung. Beim Aufrufen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts von einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client können diese Anmeldeinformationen in verwaltetem Code oder in einer Anwendungskonfigurationsdatei angegeben werden. Beim Aufrufen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst aus einer COM-Anwendung können Sie die <xref:System.ServiceModel.ComIntegration.IChannelCredentials> Schnittstelle zum Angeben von Anmeldeinformationen. In diesem Thema wird veranschaulicht verschiedene Möglichkeiten zur Angabe von Anmeldeinformationen mithilfe der <xref:System.ServiceModel.ComIntegration.IChannelCredentials> Schnittstelle.  
  
> [!NOTE]
>  <xref:System.ServiceModel.ComIntegration.IChannelCredentials> ist eine IDispatch-basierte Schnittstelle, und Sie erhalten keine IntelliSense-Funktionalität in Visual Studio-Umgebung.  
  
 In diesem Artikel verwendet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst definiert, der [Nachrichtensicherheitsbeispiel](../../../../docs/framework/wcf/samples/message-security-sample.md).  
  
### <a name="to-specify-a-client-certificate"></a>So geben Sie ein Clientzertifikat an:  
  
1.  Führen Sie die Datei Setup.bat im Nachrichtensicherheitsverzeichnis aus, um die erforderlichen Testzertifikate zu erstellen und zu installieren.  
  
2.  Öffnen Sie das Nachrichtensicherheitsprojekt.  
  
3.  Hinzufügen `[ServiceBehavior(Namespace=``http://Microsoft.ServiceModel.Samples``)]` an die `ICalculator` Schnittstellendefinition.  
  
4.  Hinzufügen `bindingNamespace=``http://Microsoft.ServiceModel.Samples` die Endpunkt-Tag in der App.config-Datei für den Dienst.  
  
5.  Erstellen Sie das Nachrichtensicherheitsbeispiel, und führen Sie Service.exe aus. Verwenden Sie Internet Explorer, und navigieren Sie zum URI des Diensts (), um die Funktion des Diensts zu überprüfen.  
  
6.  Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7.  Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse.  
  
     Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> oder <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> kann auch verwendet werden, anstelle von <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> um das Clientzertifikat festzulegen:  
  
    ```  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
>  Damit dieser Aufruf funktioniert, muss das Clientzertifikat auf dem Computer, auf dem der Client ausgeführt wird, als vertrauenswürdig eingestuft sein.  
  
> [!NOTE]
>  Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
### <a name="to-specify-user-name-and-password"></a>So geben Sie einen Benutzernamen und ein Kennwort an:  
  
1.  Ändern Sie die Datei Service App.config, um `wsHttpBinding` zu verwenden. Dies ist für die Validierung von Benutzername und Kennwort erforderlich:  
  
  
  
2.  Legen Sie `clientCredentialType` auf UserName fest:  
  
  
  
3.  Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4.  Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse. Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.  
  
    > [!NOTE]
    >  Die im Dienstmoniker in diesem Beispiel angegebene Bindung wurde in WSHttpBinding_ICalculator geändert. Beachten Sie, dass Sie einen gültigen Benutzernamen und ein Kennwort im Aufruf von angeben müssen <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.  
  
### <a name="to-specify-windows-credentials"></a>So geben Sie Windows-Anmeldeinformationen an:  
  
1.  Legen Sie `clientCredentialType` in der Datei Service App.config auf Windows fest:  
  
  
  
2.  Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```  
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3.  Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse. Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.  
  
    > [!NOTE]
    >  "Domäne", "Benutzer-ID" und "Kennwort" müssen durch gültige Werte ersetzt werden.  
  
### <a name="to-specify-an-issue-token"></a>So geben Sie ein Problemtoken an:  
  
1.  Problemtoken werden nur für Anwendungen, die verbundene Sicherheit verwenden, eingesetzt. Weitere Informationen zu verbundener Sicherheit finden Sie unter [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) und [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
     Im folgende Visual Basic-Codebeispiel veranschaulicht das Aufrufen der <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> Methode:  
  
    ```  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Weitere Informationen zu den Parametern für diese Methode finden Sie unter <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>Siehe auch  
 [Verbund](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Gewusst wie: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Gewusst wie: Erstellen eines Verbundclients](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)