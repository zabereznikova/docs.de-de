---
title: 'Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort'
description: Erfahren Sie, wie Sie einen WCF-Dienst zum Authentifizieren eines Clients mithilfe eines Windows-Domänen Benutzernamens und-Kennworts mit Beispielcode aktivieren.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 1f938f8041b2577b3705266948f29b42f23a6fd7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247246"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort

In diesem Thema wird veranschaulicht, wie ein Windows Communication Foundation (WCF)-Dienst zum Authentifizieren eines Clients mit einem Benutzernamen und einem Kennwort für Windows-Domäne aktiviert wird. Es wird davon ausgegangen, dass Sie über einen funktionsfähigen selbst gehosteten WCF-Dienst verfügen. Ein Beispiel für das Erstellen eines selbst gehosteten WCF-Dienstanbieter finden Sie unter " [Getting Started Tutorial](../getting-started-tutorial.md)". In diesem Thema wird davon ausgegangen, dass der Dienst im Code konfiguriert ist. Ein Beispiel für die Konfiguration eines ähnlichen Diensts mithilfe einer Konfigurationsdatei finden Sie unter [Message Security User Name](../samples/message-security-user-name.md).

Um einen Dienst zu konfigurieren, der seine Clients mit dem Benutzernamen und Kennwort einer Windows-Domäne authentifiziert, verwenden Sie die <xref:System.ServiceModel.WSHttpBinding> und legen die `Security.Mode`-Eigenschaft auf `Message` fest. Darüber hinaus müssen Sie ein X.509-Zertifikat angeben, das zum Verschlüsseln des Benutzernamens und Kennworts verwendet wird, während diese vom Client an den Dienst gesendet werden.

Auf dem Client muss der Benutzer zur Eingabe des Benutzernamens und Kennworts und zur Eingabe der Anmeldeinformationen für den WCF-Clientproxy aufgefordert werden.

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>So konfigurieren Sie einen WCF-Dienst für die Authentifizierung mit Windows-Domänen Benutzername und Kennwort

1. Erstellen Sie eine Instanz von <xref:System.ServiceModel.WSHttpBinding>, legen Sie den Sicherheitsmodus der Bindung auf <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType> fest, legen Sie den `ClientCredentialType` der Bindung auf <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> fest, und fügen Sie dem Diensthost mithilfe der konfigurierten Bindung einen Dienstendpunkt hinzu, wie im folgenden Code dargestellt:

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. Geben Sie das Serverzertifikat an, das zum Verschlüsseln des über die Verbindung gesendeten Benutzernamens und Kennworts verwendet wird. Dieser Code sollte direkt auf den vorangehenden Code folgen. Im folgenden Beispiel wird das Zertifikat verwendet, das von der setup.bat-Datei aus dem Beispiel für den [Nachrichten Sicherheits Benutzernamen](../samples/message-security-user-name.md) erstellt wurde:

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    Sie können ein eigenes Zertifikat verwenden, indem Sie im Code auf das eigene Zertifikat verweisen. Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie [unter Arbeiten mit Zertifikaten](working-with-certificates.md). Stellen Sie sicher, dass sich das Zertifikat im Speicher für vertrauenswürdige Personen für den lokalen Computer befindet. Führen Sie hierzu mmc.exe **aus, und**wählen Sie das Menü Element " **Snap-in hinzufügen/entfernen** " aus. Wählen Sie im Dialogfeld **Snap-Ins hinzufügen bzw. entfernen** das **Zertifikat-Snap-in** aus, und klicken Sie auf **Hinzufügen**. Wählen Sie im Dialogfeld Zertifikate-Snap-in die Option **Computer Konto**aus. Standardmäßig befindet sich das Zertifikat, das im Beispiel für Nachrichtensicherheit – Benutzername generiert wurde, im Ordner Persönlich – Zertifikate.  Sie wird in der Spalte ausgestellt für im MMC-Fenster als "localhost" aufgeführt. Ziehen Sie das Zertifikat per Drag & Drop in den Ordner **Vertrauenswürdige Personen** . Dadurch kann WCF das Zertifikat beim Ausführen einer Authentifizierung als vertrauenswürdiges Zertifikat behandeln.

## <a name="to-call-the-service-passing-username-and-password"></a>So rufen Sie den Dienst auf, der den Benutzernamen und das Kennwort übergibt

1. Die Clientanwendung muss den Benutzer zur Eingabe von Benutzername und Kennwort auffordern. Der folgende Code fragt den Benutzer nach Benutzername und Kennwort:

    > [!WARNING]
    > Dieser Code sollte nicht in Produktionssystemen verwendet werden, da das Kennwort bei der Eingabe sichtbar ist.

    ```csharp
    public static void GetPassword(out string username, out string password)
    {
        Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");
        Console.WriteLine("   Enter username:");
        username = Console.ReadLine();
        Console.WriteLine("   Enter password:");
        password = Console.ReadLine();
    }
    ```

2. Erstellen Sie eine Instanz des Client Proxys, indem Sie die Anmelde Informationen des Clients angeben, wie im folgenden Code gezeigt:

    ```csharp
    string username;
    string password;

    // Instantiate the proxy.
    var proxy = new Service1Client();

    // Prompt the user for username & password.
    GetPassword(out username, out password);

    // Set the user's credentials on the proxy.
    proxy.ClientCredentials.UserName.UserName = username;
    proxy.ClientCredentials.UserName.Password = password;

    // Treat the test certificate as trusted.
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;
    // Call the service operation using the proxy
    ```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [Transportsicherheit mit Standardauthentifizierung](transport-security-with-basic-authentication.md)
- [Sicherheit bei verteilten Anwendungen](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
