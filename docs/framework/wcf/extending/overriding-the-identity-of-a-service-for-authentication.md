---
title: Überschreiben der Identität eines Dienstes zur Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: ec1acc009e58408fc41c60134538340486f19f75
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949678"
---
# <a name="overriding-the-identity-of-a-service-for-authentication"></a>Überschreiben der Identität eines Dienstes zur Authentifizierung
In der Regel müssen Sie die Identität für einen Dienst nicht festlegen, da die Auswahl eines Clientanmeldeinformationstyps über den in den Dienstmetadaten angezeigten Identitätstyp entscheidet. Der folgende Konfigurations Code verwendet beispielsweise das [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) -Element und legt `clientCredentialType` das-Attribut auf Windows fest.  

 Das folgende Web Services Description Language (WSDL)-Fragment zeigt die Identität für den zuvor definierten Endpunkt an. In diesem Beispiel wird der Dienst als selbstgeh osteter Dienst unter einem bestimmten Benutzerkonto (username@contoso.com) ausgeführt. Daher enthält die Benutzer Prinzipal Namen-Identität (User Principal Name, UPN) den Kontonamen. Der UPN wird in einer Windows-Domäne auch als Benutzeranmeldename bezeichnet.  

 Eine Beispielanwendung, die die Identitäts Einstellung veranschaulicht, finden Sie unter [Beispiel für Dienst Identität](../../../../docs/framework/wcf/samples/service-identity-sample.md). Weitere Informationen zur Dienst Identität finden Sie unter [Dienst Identität und-Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos-Authentifizierung und Identität  
 Wenn ein Dienst für die Verwendung von Windows-Anmelde Informationen konfiguriert ist, wird standardmäßig ein [ \<Identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) -Element verwendet, das eine [ \<userPrincipalName->](../../../../docs/framework/configure-apps/file-schema/wcf/userprincipalname.md) oder [ \<ein servicePrincipalName->](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) Element enthält. wird in der WSDL-Datei generiert. Wenn der `LocalSystem`Dienst unter dem Konto, `NetworkService` `LocalService`oder ausgeführt wird, `host/` \<wird standardmäßig ein Dienst Prinzipal Name (Service Principal Name, SPN) in der Form *Hostname*> generiert, da diese Konten Zugriff auf haben. die SPN-Daten des Computers. Wenn der Dienst unter einem anderen Konto ausgeführt wird, generiert Windows Communication Foundation (WCF) \<einen UPN in der Form *Benutzername*>@<*Domain Name*`>`. Die Kerberos-Authentifizierung erfordert nämlich, dass für den Client ein UPN oder SPN zum Authentifizieren des Dienstes bereitgestellt wird.  
  
 Sie können auch das Tool Setspn.exe zur Registrierung eines zusätzlichen SPN beim Konto eines Dienstes in einer Domäne verwenden. Sie können dann den SPN als die Identität des Dienstes verwenden. Informationen zum Herunterladen des Tools [finden Sie unter Windows 2000 Resource Kit-Tool: Setspn. exe](https://go.microsoft.com/fwlink/?LinkId=91752). Weitere Informationen zum Tool finden Sie unter [setspn Overview (Übersicht über Setspn](https://go.microsoft.com/fwlink/?LinkId=61374)).  
  
> [!NOTE]
> Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Dienstes Zugriff auf den bei der Active Directory-Domäne registrierten SPN haben. Dazu stehen Ihnen folgende Möglichkeiten zur Verfügung:  
  
- Verwenden Sie das NetworkService- oder das LocalSystem-Konto, um den Dienst auszuführen. Da diese Konten Zugriff auf den Computer-SPN haben, der hergestellt wird, wenn der Computer der Active Directory Domäne Beitritt, generiert WCF automatisch das entsprechende SPN-Element innerhalb des Dienst Endpunkts in den Dienst Metadaten (WSDL).  
  
- Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen. Erstellen Sie in diesem Fall mit dem Tool Setspn.exe einen SPN für dieses Domänenkonto. Nachdem Sie den SPN für das Dienst Konto erstellt haben, konfigurieren Sie WCF so, dass dieser SPN über seine Metadaten (WSDL) auf den Clients des dienstanders veröffentlicht wird. Legen Sie dazu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.  
  
 Weitere Informationen zu SPNs, zum Kerberos-Protokoll und Active Directory finden Sie in der [technischen Ergänzung zu Kerberos für Windows](https://go.microsoft.com/fwlink/?LinkId=88330).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Wenn SPN oder UPN der leeren Zeichenfolge entspricht  
 Das Festlegen von SPN oder UPN gleich einer leeren Zeichenfolge führt abhängig von der Sicherheitsebene und dem verwendeten Authentifizierungsmodus zu verschiedenen Ergebnissen:  
  
- Wenn Sie Sicherheit auf Transportebene verwenden, wird die NT LanMan (NTLM)-Authentifizierung ausgewählt.  
  
- Wenn Sie Sicherheit auf Nachrichtenebene verwenden, schlägt die Authentifizierung abhängig vom Authentifizierungsmodus möglicherweise fehl:  
  
- Wenn Sie den `spnego`-Modus verwenden und das `AllowNtlm`-Attribut auf `false` festgelegt ist, schlägt die Authentifizierung fehl.  
  
- Verwenden Sie den `spnego`-Modus verwenden und ist das `AllowNtlm`-Attribut auf `true` festgelegt, schlägt die Authentifizierung fehl, wenn der UPN leer ist; sie ist jedoch erfolgreich, wenn der SPN leer ist.  
  
- Wenn Sie Kerberos direkt (wird auch als "One-Shot" bezeichnet) verwenden, schlägt die Authentifizierung fehl.  
  
### <a name="using-the-identity-element-in-configuration"></a>Verwenden des \<Identity >-Elements in der Konfiguration  
 Wenn Sie den Clientanmeldeinformationstyp in der zuvor gezeigten Bindung zu Certificate`,` ändern, enthält die generierte WSDL ein serialisiertes Base64-X.509-Zertifikat als Identitätswert, wie im folgenden Code gezeigt. Dies ist der Standard für alle Clientanmeldeinformationstypen außer Windows.  

 Sie können den Wert der Standard Dienst Identität ändern oder den Typ der Identität ändern, indem Sie das <`identity`>-Element in der Konfiguration verwenden oder die Identität im Code festlegen. Der folgende Konfigurationscode legt eine DNS-Identität (Domain Name System) mit dem Wert `contoso.com` fest.  

### <a name="setting-identity-programmatically"></a>Programmgesteuertes Festlegen der Identität  
 Ihr Dienst muss eine Identität nicht explizit angeben, da Sie von WCF automatisch bestimmt wird. WCF ermöglicht es Ihnen jedoch, eine Identität für einen Endpunkt anzugeben, falls dies erforderlich ist. Mit dem folgenden Code wird ein neuer Dienstendpunkt mit einer bestimmten DNS-Identität hinzugefügt.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Client Identitätsüberprüfung](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)
- [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
