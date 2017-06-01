---
title: "&#220;berschreiben der Identit&#228;t eines Dienstes zur Authentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &#220;berschreiben der Identit&#228;t eines Dienstes zur Authentifizierung
In der Regel müssen Sie die Identität für einen Dienst nicht festlegen, da die Auswahl eines Clientanmeldeinformationstyps über den in den Dienstmetadaten angezeigten Identitätstyp entscheidet. Der folgende Konfigurationscode verwendet beispielsweise die [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element und legt die `clientCredentialType` -Attribut auf Windows.  
  
  
  
 Das folgende Web Services Description Language (WSDL)-Fragment zeigt die Identität für den zuvor definierten Endpunkt an. In diesem Beispiel wird der Dienst als selbst gehosteter Dienst unter einem bestimmten Benutzerkonto ausgeführt (username@contoso.com) und daher die Identität des Benutzers Benutzerprinzipalnamen (UPN) enthält den Kontonamen. Der UPN wird in einer Windows-Domäne auch als Benutzeranmeldename bezeichnet.  
  
  
  
 Ein beispielanwendung, die identitätseinstellung veranschaulicht, finden Sie unter [Dienstidentitätsbeispiel](../../../../docs/framework/wcf/samples/service-identity-sample.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Dienstidentität, finden Sie unter [-Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos-Authentifizierung und Identität  
 Wenn ein Dienst so konfiguriert ist, Windows-Anmeldeinformationen verwenden, wird standardmäßig ein [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) -Element, enthält eine [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) oder [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) Element in die WSDL-Datei generiert wird. Wenn der Dienst, unter ausgeführt wird der `LocalSystem`, `LocalService`, oder `NetworkService` -Konto, ein Dienst, der Dienstprinzipalnamen (SPN) wird standardmäßig, in Form von generiert `host/` \< *Hostname*> da diese Konten Zugriff auf den Computer-SPN-Daten haben. Wenn der Dienst unter einem anderen Konto ausgeführt wird [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] generiert einen UPN im Format *Benutzername*>@<*DomainName*`>`. Die Kerberos-Authentifizierung erfordert nämlich, dass für den Client ein UPN oder SPN zum Authentifizieren des Dienstes bereitgestellt wird.  
  
 Sie können auch das Tool Setspn.exe zur Registrierung eines zusätzlichen SPN beim Konto eines Dienstes in einer Domäne verwenden. Sie können dann den SPN als die Identität des Dienstes verwenden. Zum Herunterladen des Tools finden Sie unter [Windows 2000 Resource Kit Tool: Setspn.exe](http://go.microsoft.com/fwlink/?LinkId=91752). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Das Tool finden Sie unter [Setspn Overview](http://go.microsoft.com/fwlink/?LinkId=61374).  
  
> [!NOTE]
>  Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Dienstes Zugriff auf den bei der Active Directory-Domäne registrierten SPN haben. Dazu stehen Ihnen folgende Möglichkeiten zur Verfügung:  
  
-   Verwenden Sie das NetworkService- oder das LocalSystem-Konto, um den Dienst auszuführen. Da diese Konten Zugriff auf den beim Hinzufügen des Computers zur Active Directory-Domäne erstellten Computer-SPN haben, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatisch das zutreffende SPN-Element im Endpunkt des Dienstes in den Dienstmetadaten (WSDL).  
  
-   Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen. Erstellen Sie in diesem Fall mit dem Tool Setspn.exe einen SPN für dieses Domänenkonto. Konfigurieren Sie nach dem Erstellen des SPN für das Konto des Dienstes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] so, dass dieser SPN für die Clients des Dienstes über seine Metadaten (WSDL) veröffentlicht wird. Legen Sie dazu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SPNs, Kerberos-Protokoll und Active Directory finden Sie unter [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Wenn SPN oder UPN der leeren Zeichenfolge entspricht  
 Das Festlegen von SPN oder UPN gleich einer leeren Zeichenfolge führt abhängig von der Sicherheitsebene und dem verwendeten Authentifizierungsmodus zu verschiedenen Ergebnissen:  
  
-   Wenn Sie Sicherheit auf Transportebene verwenden, wird die NT LanMan (NTLM)-Authentifizierung ausgewählt.  
  
-   Wenn Sie Sicherheit auf Nachrichtenebene verwenden, schlägt die Authentifizierung abhängig vom Authentifizierungsmodus möglicherweise fehl:  
  
-   Wenn Sie den `spnego`-Modus verwenden und das `AllowNtlm`-Attribut auf `false` festgelegt ist, schlägt die Authentifizierung fehl.  
  
-   Verwenden Sie den `spnego`-Modus verwenden und ist das `AllowNtlm`-Attribut auf `true` festgelegt, schlägt die Authentifizierung fehl, wenn der UPN leer ist; sie ist jedoch erfolgreich, wenn der SPN leer ist.  
  
-   Wenn Sie Kerberos direkt (wird auch als "One-Shot" bezeichnet) verwenden, schlägt die Authentifizierung fehl.  
  
### <a name="using-the-identity-element-in-configuration"></a>Mithilfe der <> \> Element in der Konfiguration  
 Wenn Sie den Clientanmeldeinformationstyp in der zuvor gezeigten Bindung zu Certificate`,` ändern, enthält die generierte WSDL ein serialisiertes Base64-X.509-Zertifikat als Identitätswert, wie im folgenden Code gezeigt. Dies ist der Standard für alle Clientanmeldeinformationstypen außer Windows.  
  
  
  
 Sie können den Wert der standardmäßigen Dienstidentität oder den Typ der Identität mit dem <`identity`>-Element bei der Konfiguration oder durch Festlegen der Identität im Code ändern. Der folgende Konfigurationscode legt eine DNS-Identität (Domain Name System) mit dem Wert `contoso.com` fest.  
  
  
  
### <a name="setting-identity-programmatically"></a>Programmgesteuertes Festlegen der Identität  
 Der Dienst muss nicht explizit eine Identität angeben, da sie von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatisch bestimmt wird. Allerdings können Sie mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach Bedarf eine Identität für einen Endpunkt angeben. Mit dem folgenden Code wird ein neuer Dienstendpunkt mit einer bestimmten DNS-Identität hinzugefügt.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: erstellen eine benutzerdefinierten Clientidentitätsüberprüfung](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)   
 [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)