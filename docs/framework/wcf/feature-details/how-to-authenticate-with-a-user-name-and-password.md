---
title: "Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Authentifizierung [WCF], Benutzername und Kennwort"
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort
In diesem Thema wird veranschaulicht, wie Sie einem Dienst von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] die Authentifizierung eines Clients mit einem Benutzernamen und einem Kennwort einer Windows\-Domäne ermöglichen.Es wird davon ausgegangen, dass Sie über einen funktionierenden selbst\-gehosteten WCF\-Dienst verfügen.Ein Beispiel für das Erstellen eines selbst\-gehosteten WCF\-Basisdiensts finden Sie unter [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md).In diesem Thema wird davon ausgegangen, dass der Dienst im Code konfiguriert ist.Ein Beispiel für das Konfigurieren eines ähnlichen Diensts mit einer Konfigurationsdatei finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md).  
  
 Um einen Dienst zu konfigurieren, der seine Clients mit dem Benutzernamen und Kennwort einer Windows\-Domäne authentifiziert, verwenden Sie <xref:System.ServiceModel.WSHttpBinding> und legen die `Security.Mode`\-Eigenschaft auf `Message` fest.Darüber hinaus müssen Sie ein X.509\-Zertifikat angeben, das zum Verschlüsseln von Benutzernamen und Kennwort verwendet wird, während diese vom Client an den Dienst gesendet werden.  
  
 Auf dem Client muss der Benutzer zur Eingabe von Anmeldenamen und Kennwort und zur Eingabe der Anmeldeinformationen für den WCF\-Clientproxy aufgefordert werden.  
  
### So erstellen Sie einen WCF\-Dienst, der zur Authentifizierung den Benutzernamen und das Kennwort einer Windows\-Domäne verwendet.  
  
1.  Erstellen Sie eine Instanz von <xref:System.ServiceModel.WSHttpBinding>, legen Sie den Sicherheitsmodus der Bindung auf `SecurityMode.Message` fest, legen Sie `ClientCredentialType` der Bindung an `MessageCredentialType.UserName` fest, und fügen Sie dem Diensthost einen Dienstendpunkt unter Verwendung der konfigurierten Bindung hinzu wie im folgenden Code dargestellt:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Geben Sie das Serverzertifikat an, das zum Verschlüsseln des über die Verbindung gesendeten Benutzernamens und Kennworts verwendet wird.Dieser Code sollte direkt auf den vorangehenden Code folgen.Im folgenden Beispiel wird das Zertifikat verwendet, das von der Datei setup.bat\-Datei aus dem Beispiel [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md) erstellt wurde:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     Sie können ein eigenes Zertifikat verwenden, indem Sie im Code einen Verweis auf Ihr eigenes Zertifikat setzen.Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).Stellen Sie sicher, dass sich das das Zertifikat im Speicher für vertrauenswürdige Personen für den lokalen Computer befindet.Dazu können Sie mmc.exe ausführen und im Menü **Datei** das Menüelement **Snap\-In hinzufügen\/entfernen** auswählen.Wählen Sie im Dialogfeld **Snap\-In hinzufügen\/entfernen** die Option **Zertifikat\-Snap\-In** aus, und klicken Sie auf **Hinzufügen**.Wählen Sie im Dialogfeld **Zertifikat\-Snap\-In** die Option **Computerkonto** aus.Standardmäßig befindet sich das Zertifikat, das im Beispiel für Nachrichtensicherheit – Benutzername generiert wurde, im Ordner **Persönlich – Zertifikate**.Es wird als "localhost" in der Spalte **Ausgestellt für** im MMC\-Fenster aufgelistet.Ziehen Sie das Zertifikat auf den Ordner **Vertrauenswürdige Personen**, und legen Sie es dort ab.Dadurch kann WCF das Zertifikat beim Ausführen einer Authentifizierung als vertrauenswürdiges Zertifikat behandeln.  
  
### So rufen Sie den Dienst auf, der den Benutzername und das Kennwort übergibt  
  
1.  Die Clientanwendung muss den Benutzer zur Eingabe von Benutzernamen und Kennwort auffordern.Der folgende Code fordert den Benutzer zur Eingabe von Benutzernamen und Kennwort auf.  
  
    > [!WARNING]
    >  Dieser Code sollte nicht in Produktionssystemen verwendet werden, da das Kennwort bei der Eingabe sichtbar ist.  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
  
    ```  
  
2.  Erstellen Sie eine Instanz des Clientproxys, indem Sie die Anmeldeinformationen des Clients wie im folgenden Code dargestellt angeben:  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## Siehe auch  
 <xref:System.ServiceModel.WsHttpBinding>   
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.SecurityMode>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>   
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>   
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>   
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>   
 [Transportsicherheit mit Standardauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)   
 [Sicherheit bei verteilten Anwendungen](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)   
 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)