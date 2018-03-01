---
title: 'Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1554e8594a611aa75876d14ee7ad0689932372e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="69dde-102">Vorgehensweise: Authentifizierung mit Benutzernamen und Kennwort</span><span class="sxs-lookup"><span data-stu-id="69dde-102">How to: Authenticate with a User Name and Password</span></span>
<span data-ttu-id="69dde-103">In diesem Thema wird veranschaulicht, wie Sie einem Dienst von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] die Authentifizierung eines Clients mit einem Benutzernamen und einem Kennwort einer Windows-Domäne ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="69dde-103">This topic demonstrates how to enable a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="69dde-104">Es wird davon ausgegangen, dass Sie über einen funktionsfähigen selbst gehosteten WCF-Dienst verfügen.</span><span class="sxs-lookup"><span data-stu-id="69dde-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="69dde-105">Ein Beispiel zum Erstellen einer grundlegenden selbst gehosteten WCF-Dienst finden Sie unter [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="69dde-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="69dde-106">In diesem Thema wird davon ausgegangen, dass der Dienst im Code konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="69dde-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="69dde-107">Wenn Sie möchten, finden ein Beispiel zum Konfigurieren eines ähnlichen Diensts mithilfe einer Konfigurationsdatei finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="69dde-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="69dde-108">So konfigurieren Sie einen Dienst, um seinen Clients verwenden Sie Benutzernamen und Kennwörter mithilfe von Windows-Domäne authentifizieren der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, und legen seine `Security.Mode` Eigenschaft `Message`.</span><span class="sxs-lookup"><span data-stu-id="69dde-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="69dde-109">Darüber hinaus müssen Sie ein X.509-Zertifikat angeben, das zum Verschlüsseln des Benutzernamens und Kennworts verwendet wird, während diese vom Client an den Dienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="69dde-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="69dde-110">Auf dem Client muss der Benutzer zur Eingabe des Benutzernamens und Kennworts und zur Eingabe der Anmeldeinformationen für den WCF-Clientproxy aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="69dde-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="69dde-111">So konfigurieren Sie einen WCF-Dienst für die Authentifizierung mit dem Benutzernamen und Kennwort einer Windows-Domäne</span><span class="sxs-lookup"><span data-stu-id="69dde-111">To configure a WCF service to authenticate using Windows domain username and password.</span></span>  
  
1.  <span data-ttu-id="69dde-112">Erstellen Sie eine Instanz von der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, Festlegen des Sicherheitsmodus der Bindung, die `SecurityMode.Message`legen die `ClientCredentialType` Bindung mit `MessageCredentialType.UserName`, und fügen Sie einen Dienstendpunkt wie gezeigt, über die konfigurierte Bindung an den Diensthost Im folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="69dde-112">Create an instance of the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, set the security mode of the binding to `SecurityMode.Message`, set the `ClientCredentialType` of the binding to `MessageCredentialType.UserName`, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="69dde-113">Geben Sie das Serverzertifikat an, das zum Verschlüsseln des über die Verbindung gesendeten Benutzernamens und Kennworts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69dde-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="69dde-114">Dieser Code sollte direkt auf den vorangehenden Code folgen.</span><span class="sxs-lookup"><span data-stu-id="69dde-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="69dde-115">Im folgenden Beispiel wird das Zertifikat, das erstellt wird, indem Sie die Datei "Setup.bat" aus der [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md) Beispiel:</span><span class="sxs-lookup"><span data-stu-id="69dde-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="69dde-116">Sie können ein eigenes Zertifikat verwenden, indem Sie im Code auf das eigene Zertifikat verweisen.</span><span class="sxs-lookup"><span data-stu-id="69dde-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="69dde-117">Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="69dde-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="69dde-118">Stellen Sie sicher, dass sich das Zertifikat im Speicher für vertrauenswürdige Personen für den lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="69dde-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="69dde-119">Hierzu können Sie durch Ausführen von mmc.exe und Auswählen der **Datei**, **Snap-In hinzufügen/entfernen...**  Menüelement.</span><span class="sxs-lookup"><span data-stu-id="69dde-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="69dde-120">In der **hinzufügen oder Entfernen von Snap-Ins** wählen Sie im Dialogfeld die **Zertifikat-Snap-in** , und klicken Sie auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69dde-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="69dde-121">Wählen Sie im Dialogfeld "Zertifikat-Snap-in" **Computerkonto**.</span><span class="sxs-lookup"><span data-stu-id="69dde-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="69dde-122">Standardmäßig befindet sich das Zertifikat, das im Beispiel für Nachrichtensicherheit – Benutzername generiert wurde, im Ordner Persönlich – Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="69dde-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="69dde-123">Es wird als "Localhost", unter der Spalte im MMC-Fenster ausgestellt für angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="69dde-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="69dde-124">Ziehen Sie das Zertifikat in der **vertrauenswürdige Personen** Ordner.</span><span class="sxs-lookup"><span data-stu-id="69dde-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="69dde-125">Dadurch kann WCF das Zertifikat beim Ausführen einer Authentifizierung als vertrauenswürdiges Zertifikat behandeln.</span><span class="sxs-lookup"><span data-stu-id="69dde-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
### <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="69dde-126">So rufen Sie den Dienst auf, der den Benutzernamen und das Kennwort übergibt</span><span class="sxs-lookup"><span data-stu-id="69dde-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="69dde-127">Die Clientanwendung muss den Benutzer zur Eingabe von Benutzername und Kennwort auffordern.</span><span class="sxs-lookup"><span data-stu-id="69dde-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="69dde-128">Der folgende Code fordert den Benutzer zur Eingabe von Benutzername und Kennwort auf.</span><span class="sxs-lookup"><span data-stu-id="69dde-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="69dde-129">Dieser Code sollte nicht in Produktionssystemen verwendet werden, da das Kennwort bei der Eingabe sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="69dde-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
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
  
2.  <span data-ttu-id="69dde-130">Erstellen Sie eine Instanz des Clientproxys, indem Sie die Anmeldeinformationen des Clients wie im folgenden Code dargestellt angeben:</span><span class="sxs-lookup"><span data-stu-id="69dde-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69dde-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69dde-131">See Also</span></span>  
 <span data-ttu-id="69dde-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="69dde-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [<span data-ttu-id="69dde-133">Transportsicherheit mit Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="69dde-133">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [<span data-ttu-id="69dde-134">Sicherheit bei verteilten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="69dde-134">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="69dde-135">\<WsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="69dde-135">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
