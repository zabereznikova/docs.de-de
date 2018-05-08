---
title: 'Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort'
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: b37d296312be4c7694a2db55d85dd618e3252f14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort

In diesem Thema veranschaulicht, wie einen Windows Communication Foundation (WCF)-Dienst zum Authentifizieren eines Clients mit einem Windows-Domänenbenutzernamen und Kennwort. Es wird davon ausgegangen, dass Sie über einen funktionsfähigen selbst gehosteten WCF-Dienst verfügen. Ein Beispiel zum Erstellen einer grundlegenden selbst gehosteten WCF-Dienst finden Sie unter [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md). In diesem Thema wird davon ausgegangen, dass der Dienst im Code konfiguriert ist. Wenn Sie möchten, finden ein Beispiel zum Konfigurieren eines ähnlichen Diensts mithilfe einer Konfigurationsdatei finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Um einen Dienst zu konfigurieren, der seine Clients mit dem Benutzernamen und Kennwort einer Windows-Domäne authentifiziert, verwenden Sie die <xref:System.ServiceModel.WSHttpBinding> und legen die `Security.Mode`-Eigenschaft auf `Message` fest. Darüber hinaus müssen Sie ein X.509-Zertifikat angeben, das zum Verschlüsseln des Benutzernamens und Kennworts verwendet wird, während diese vom Client an den Dienst gesendet werden.  
  
 Auf dem Client muss der Benutzer zur Eingabe des Benutzernamens und Kennworts und zur Eingabe der Anmeldeinformationen für den WCF-Clientproxy aufgefordert werden.  
  
## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>So konfigurieren Sie einen WCF-Dienst die Authentifizierung mit Windows-Domänenbenutzernamen und Kennwort
  
1.  Erstellen Sie eine Instanz von <xref:System.ServiceModel.WSHttpBinding>, legen Sie den Sicherheitsmodus der Bindung auf `SecurityMode.Message` fest, legen Sie den `ClientCredentialType` der Bindung auf `MessageCredentialType.UserName` fest, und fügen Sie dem Diensthost mithilfe der konfigurierten Bindung einen Dienstendpunkt hinzu, wie im folgenden Code dargestellt:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Geben Sie das Serverzertifikat an, das zum Verschlüsseln des über die Verbindung gesendeten Benutzernamens und Kennworts verwendet wird. Dieser Code sollte direkt auf den vorangehenden Code folgen. Im folgenden Beispiel wird das Zertifikat, das erstellt wird, indem Sie die Datei "Setup.bat" aus der [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md) Beispiel:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     Sie können ein eigenes Zertifikat verwenden, indem Sie im Code auf das eigene Zertifikat verweisen. Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Stellen Sie sicher, dass sich das Zertifikat im Speicher für vertrauenswürdige Personen für den lokalen Computer befindet. Hierzu können Sie durch Ausführen von mmc.exe und Auswählen der **Datei**, **Snap-In hinzufügen/entfernen...**  Menüelement. In der **hinzufügen oder Entfernen von Snap-Ins** wählen Sie im Dialogfeld die **Zertifikat-Snap-in** , und klicken Sie auf **hinzufügen**. Wählen Sie im Dialogfeld "Zertifikat-Snap-in" **Computerkonto**. Standardmäßig befindet sich das Zertifikat, das im Beispiel für Nachrichtensicherheit – Benutzername generiert wurde, im Ordner Persönlich – Zertifikate.  Es wird als "Localhost", unter der Spalte im MMC-Fenster ausgestellt für angezeigt werden. Ziehen Sie das Zertifikat in der **vertrauenswürdige Personen** Ordner. Dadurch kann WCF das Zertifikat beim Ausführen einer Authentifizierung als vertrauenswürdiges Zertifikat behandeln.  
  
## <a name="to-call-the-service-passing-username-and-password"></a>So rufen Sie den Dienst auf, der den Benutzernamen und das Kennwort übergibt  
  
1.  Die Clientanwendung muss den Benutzer zur Eingabe von Benutzername und Kennwort auffordern. Der folgende Code fordert den Benutzer zur Eingabe von Benutzername und Kennwort auf.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [Transportsicherheit mit Standardauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [Sicherheit bei verteilten Anwendungen](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
