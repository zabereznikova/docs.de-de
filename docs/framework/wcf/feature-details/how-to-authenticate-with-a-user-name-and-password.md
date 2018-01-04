---
title: 'Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1554e8594a611aa75876d14ee7ad0689932372e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort
In diesem Thema wird veranschaulicht, wie Sie einem Dienst von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] die Authentifizierung eines Clients mit einem Benutzernamen und einem Kennwort einer Windows-Domäne ermöglichen. Es wird davon ausgegangen, dass Sie über einen funktionsfähigen selbst gehosteten WCF-Dienst verfügen. Ein Beispiel zum Erstellen einer grundlegenden selbst gehosteten WCF-Dienst finden Sie unter [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md). In diesem Thema wird davon ausgegangen, dass der Dienst im Code konfiguriert ist. Wenn Sie möchten, finden ein Beispiel zum Konfigurieren eines ähnlichen Diensts mithilfe einer Konfigurationsdatei finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 So konfigurieren Sie einen Dienst, um seinen Clients verwenden Sie Benutzernamen und Kennwörter mithilfe von Windows-Domäne authentifizieren der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, und legen seine `Security.Mode` Eigenschaft `Message`. Darüber hinaus müssen Sie ein X.509-Zertifikat angeben, das zum Verschlüsseln des Benutzernamens und Kennworts verwendet wird, während diese vom Client an den Dienst gesendet werden.  
  
 Auf dem Client muss der Benutzer zur Eingabe des Benutzernamens und Kennworts und zur Eingabe der Anmeldeinformationen für den WCF-Clientproxy aufgefordert werden.  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>So konfigurieren Sie einen WCF-Dienst für die Authentifizierung mit dem Benutzernamen und Kennwort einer Windows-Domäne  
  
1.  Erstellen Sie eine Instanz von der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, Festlegen des Sicherheitsmodus der Bindung, die `SecurityMode.Message`legen die `ClientCredentialType` Bindung mit `MessageCredentialType.UserName`, und fügen Sie einen Dienstendpunkt wie gezeigt, über die konfigurierte Bindung an den Diensthost Im folgenden Code:  
  
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
  
### <a name="to-call-the-service-passing-username-and-password"></a>So rufen Sie den Dienst auf, der den Benutzernamen und das Kennwort übergibt  
  
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
 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [Transportsicherheit mit Standardauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [Sicherheit bei verteilten Anwendungen](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [\<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
