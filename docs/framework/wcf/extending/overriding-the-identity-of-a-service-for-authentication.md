---
title: Überschreiben der Identität eines Dienstes zur Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: 3ac2d48962dd96535e1a08310570212121eca986
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555418"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>Überschreiben der Identität eines Dienstanbieter für die Authentifizierung

In der Regel müssen Sie die Identität für einen Dienst nicht festlegen, da die Auswahl eines Clientanmeldeinformationstyps über den in den Dienstmetadaten angezeigten Identitätstyp entscheidet. Der folgende Konfigurations Code verwendet beispielsweise das [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) -Element und legt das- `clientCredentialType` Attribut auf Windows fest.  

 Das folgende Web Services Description Language (WSDL)-Fragment zeigt die Identität für den zuvor definierten Endpunkt an. In diesem Beispiel wird der Dienst als selbstgeh osteter Dienst unter einem bestimmten Benutzerkonto () ausgeführt username@contoso.com . Daher enthält die Benutzer Prinzipal Namen-Identität (User Principal Name, UPN) den Kontonamen. Der UPN wird auch als Benutzer Anmelde Name in einer Windows-Domäne bezeichnet.  

 Eine Beispielanwendung, die die Identitäts Einstellung veranschaulicht, finden Sie unter [Beispiel für Dienst Identität](../samples/service-identity-sample.md). Weitere Informationen zur Dienst Identität finden Sie unter [Dienst Identität und-Authentifizierung](../feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos-Authentifizierung und Identität  
 Wenn ein Dienst für die Verwendung von Windows-Anmelde Informationen konfiguriert ist, wird standardmäßig ein [\<identity>](../../configure-apps/file-schema/wcf/identity.md) Element generiert, das ein- [\<userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) Element oder ein- [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) Element in der WSDL-Datei enthält. Wenn der Dienst unter dem `LocalSystem` Konto, oder ausgeführt wird `LocalService` `NetworkService` , wird standardmäßig ein Dienst Prinzipal Name (Service Principal Name, SPN) in der Form von generiert, `host/` \<*hostname*> da diese Konten Zugriff auf die SPN-Daten des Computers haben. Wenn der Dienst unter einem anderen Konto ausgeführt wird, generiert Windows Communication Foundation (WCF) einen UPN im Format \<*username*> @< *Domain Name* `>` . Die Kerberos-Authentifizierung erfordert nämlich, dass für den Client ein UPN oder SPN zum Authentifizieren des Dienstes bereitgestellt wird.  
  
 Sie können auch das [setspn](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)) -Tool verwenden, um einen zusätzlichen SPN bei einem Dienst Konto in einer Domäne zu registrieren. Sie können dann den SPN als die Identität des Dienstes verwenden. Weitere Informationen zum Tool finden Sie unter [setspn Overview (Übersicht über Setspn](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))).  
  
> [!NOTE]
> Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Dienstes Zugriff auf den bei der Active Directory-Domäne registrierten SPN haben. Dazu stehen Ihnen folgende Möglichkeiten zur Verfügung:  
  
- Verwenden Sie das NetworkService- oder das LocalSystem-Konto, um den Dienst auszuführen. Da diese Konten Zugriff auf den Computer-SPN haben, der hergestellt wird, wenn der Computer der Active Directory Domäne Beitritt, generiert WCF automatisch das entsprechende SPN-Element innerhalb des Dienst Endpunkts in den Dienst Metadaten (WSDL).  
  
- Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen. Erstellen Sie in diesem Fall mit dem Tool Setspn.exe einen SPN für dieses Domänenkonto. Nachdem Sie den SPN für das Dienst Konto erstellt haben, konfigurieren Sie WCF so, dass dieser SPN über seine Metadaten (WSDL) auf den Clients des dienstanders veröffentlicht wird. Legen Sie dazu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.  
  
 Weitere Informationen zu SPNs, zum Kerberos-Protokoll und Active Directory finden Sie in der [technischen Ergänzung zu Kerberos für Windows](/previous-versions/msp-n-p/ff649429(v=pandp.10)).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Wenn SPN oder UPN der leeren Zeichenfolge entspricht  
 Das Festlegen von SPN oder UPN gleich einer leeren Zeichenfolge führt abhängig von der Sicherheitsebene und dem verwendeten Authentifizierungsmodus zu verschiedenen Ergebnissen:  
  
- Wenn Sie Sicherheit auf Transportebene verwenden, wird die NT LanMan (NTLM)-Authentifizierung ausgewählt.  
  
- Wenn Sie Sicherheit auf Nachrichtenebene verwenden, schlägt die Authentifizierung abhängig vom Authentifizierungsmodus möglicherweise fehl:  
  
- Wenn Sie `spnego` den-Modus verwenden und das- `AllowNtlm` Attribut auf festgelegt ist `false` , schlägt die Authentifizierung fehl.  
  
- Wenn Sie den `spnego` -Modus verwenden und das- `AllowNtlm` Attribut auf festgelegt ist `true` , schlägt die Authentifizierung fehl, wenn der UPN leer ist, aber erfolgreich ist, wenn der SPN leer ist.  
  
- Wenn Sie Kerberos direkt (wird auch als "One-Shot" bezeichnet) verwenden, schlägt die Authentifizierung fehl.  
  
### <a name="use-the-identity-element-in-configuration"></a>Verwenden Sie das- \<identity> Element in der Konfiguration  
 Wenn Sie den Client Anmelde Informationstyp in der zuvor gezeigten Bindung in ändern `Certificate` , enthält die generierte WSDL ein serialisiertes Base64-X. 509-Zertifikat für den Identitäts Wert, wie im folgenden Code gezeigt. Dies ist der Standard für alle Clientanmeldeinformationstypen außer Windows.  

 Sie können den Wert der Standard Dienst Identität ändern oder den Typ der Identität ändern, indem Sie das <`identity`>-Element in der Konfiguration verwenden oder die Identität im Code festlegen. Der folgende Konfigurationscode legt eine DNS-Identität (Domain Name System) mit dem Wert `contoso.com` fest.  

### <a name="set-identity-programmatically"></a>Programm gesteuertes Festlegen der Identität  
 Ihr Dienst muss eine Identität nicht explizit angeben, da Sie von WCF automatisch bestimmt wird. WCF ermöglicht es Ihnen jedoch, ggf. eine Identität für einen Endpunkt anzugeben. Mit dem folgenden Code wird ein neuer Dienstendpunkt mit einer bestimmten DNS-Identität hinzugefügt.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung](how-to-create-a-custom-client-identity-verifier.md)
- [Dienstidentität und Authentifizierung](../feature-details/service-identity-and-authentication.md)
