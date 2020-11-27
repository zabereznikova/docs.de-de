---
title: 'Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 9236985ef461044e480847003d9d249b7e232783
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266765"
---
# <a name="how-to-specify-channel-security-credentials"></a>Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit

Der Windows Communication Foundation (WCF)-Dienstmoniker ermöglicht com-Anwendungen das Aufrufen von WCF-Diensten. Die meisten WCF-Dienste erfordern, dass der Client Anmelde Informationen für die Authentifizierung und Autorisierung angibt. Wenn Sie einen WCF-Dienst von einem WCF-Client aufrufen, können Sie diese Anmelde Informationen in verwaltetem Code oder in einer Anwendungs Konfigurationsdatei angeben. Wenn Sie einen WCF-Dienst aus einer COM-Anwendung aufrufen, können Sie die- <xref:System.ServiceModel.ComIntegration.IChannelCredentials> Schnittstelle verwenden, um Anmelde Informationen anzugeben. In diesem Thema werden verschiedene Möglichkeiten zur Angabe von Anmeldeinformationen mithilfe der <xref:System.ServiceModel.ComIntegration.IChannelCredentials>-Schnittstelle erläutert.  
  
> [!NOTE]
> <xref:System.ServiceModel.ComIntegration.IChannelCredentials> ist eine IDispatch-basierte Schnittstelle, und Sie erhalten keine IntelliSense-Funktionen in der Visual Studio-Umgebung.  
  
 In diesem Artikel wird der im [Nachrichten Sicherheits Beispiel](../samples/message-security-sample.md)definierte WCF-Dienst verwendet.  
  
### <a name="to-specify-a-client-certificate"></a>So geben Sie ein Clientzertifikat an:  
  
1. Führen Sie die Datei Setup.bat im Nachrichtensicherheitsverzeichnis aus, um die erforderlichen Testzertifikate zu erstellen und zu installieren.  
  
2. Öffnen Sie das Nachrichtensicherheitsprojekt.  
  
3. Fügen Sie `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` der `ICalculator` Schnittstellen Definition hinzu.  
  
4. Fügen Sie `bindingNamespace="http://Microsoft.ServiceModel.Samples"` dem Endpunkt-Tag in der App.config für den Dienst hinzu.  
  
5. Erstellen Sie das Nachrichtensicherheitsbeispiel, und führen Sie Service.exe aus. Verwenden Sie Internet Explorer, und navigieren Sie zum URI des dienstangs ( `http://localhost:8000/ServiceModelSamples/Service` ), um sicherzustellen, dass der Dienst funktioniert.  
  
6. Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```vb  
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
  
7. Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse.  
  
     Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an. <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> oder <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> können anstelle von <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> verwendet werden, um das Clientzertifikat festzulegen:  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> Damit dieser Aufruf funktioniert, muss das Clientzertifikat auf dem Computer, auf dem der Client ausgeführt wird, als vertrauenswürdig eingestuft sein.  
  
> [!NOTE]
> Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
### <a name="to-specify-user-name-and-password"></a>So geben Sie einen Benutzernamen und ein Kennwort an:  
  
1. Ändern Sie die Datei Service App.config, um `wsHttpBinding` zu verwenden. Dies ist für die Validierung von Benutzername und Kennwort erforderlich:  

2. Legen Sie `clientCredentialType` auf UserName fest:  

3. Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse. Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.  
  
    > [!NOTE]
    > Die im Dienstmoniker in diesem Beispiel angegebene Bindung wurde in WSHttpBinding_ICalculator geändert. Zudem müssen beim Aufruf von <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> ein gültiger Benutzername und ein Kennwort angegeben werden.  
  
### <a name="to-specify-windows-credentials"></a>So geben Sie Windows-Anmeldeinformationen an:  
  
1. Legen Sie `clientCredentialType` in der Datei Service App.config auf Windows fest:  

2. Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse. Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.  
  
    > [!NOTE]
    > "Domäne", "Benutzer-ID" und "Kennwort" müssen durch gültige Werte ersetzt werden.  
  
### <a name="to-specify-an-issue-token"></a>So geben Sie ein Problemtoken an:  
  
1. Problemtoken werden nur für Anwendungen, die verbundene Sicherheit verwenden, eingesetzt. Weitere Informationen zur Verbund Sicherheit finden Sie unter Verbund [-und ausgestellte Token](federation-and-issued-tokens.md) und Verbund [Beispiel](../samples/federation-sample.md).  
  
     Im folgenden Visual Basic-Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>-Methode aufgerufen wird:  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     Weiter Informationen zu den Parametern für diese Methode finden Sie unter <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verbund](federation.md)
- [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](how-to-configure-credentials-on-a-federation-service.md)
- [Vorgehensweise: Erstellen eines Verbundclients](how-to-create-a-federated-client.md)
- [Nachrichtensicherheit](message-security-in-wcf.md)
- [Bindungen und Sicherheit](bindings-and-security.md)
