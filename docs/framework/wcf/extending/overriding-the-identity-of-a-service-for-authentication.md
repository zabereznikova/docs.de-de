---
title: Überschreiben der Identität eines Dienstes zur Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: e7273c1e140e52eb37a30b6cabeb9e9a83a6fa2d
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121561"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>Überschreiben der Identität eines Dienstes für die Authentifizierung

In der Regel müssen Sie die Identität für einen Dienst nicht festlegen, da die Auswahl eines Clientanmeldeinformationstyps über den in den Dienstmetadaten angezeigten Identitätstyp entscheidet. Der folgende Konfigurationscode verwendet beispielsweise das `clientCredentialType` [ \<>-Element wsHttpBinding](../../configure-apps/file-schema/wcf/wshttpbinding.md) und legt das Attribut auf Windows fest.  

 Das folgende Web Services Description Language (WSDL)-Fragment zeigt die Identität für den zuvor definierten Endpunkt an. In diesem Beispiel wird der Dienst als selbst gehosteter Dienstusername@contoso.comunter einem bestimmten Benutzerkonto ( ) ausgeführt, und daher enthält die Benutzerprinzipalname-Identität (UPN) den Kontonamen. Der UPN wird in einer Windows-Domäne auch als Benutzeranmeldename bezeichnet.  

 Eine Beispielanwendung, die die Identitätseinstellung veranschaulicht, finden Sie unter [Dienstidentitätsbeispiel](../samples/service-identity-sample.md). Weitere Informationen zur Dienstidentität finden Sie unter [Dienstidentität und Authentifizierung](../feature-details/service-identity-and-authentication.md).  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos-Authentifizierung und Identität  
 Wenn ein Dienst für die Verwendung von Windows-Anmeldeinformationen konfiguriert ist, wird standardmäßig eine [ \<Identität>](../../configure-apps/file-schema/wcf/identity.md) Element generiert, das einen [ \<userPrincipalName>](../../configure-apps/file-schema/wcf/userprincipalname.md) oder [ \<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) Element enthält. Wenn der Dienst unter `LocalSystem` `LocalService`, `NetworkService` oder Konto ausgeführt wird, wird standardmäßig ein Dienstprinzipalname (Service Principal Name, SPN) in Form von `host/` \< *Hostname*> generiert, da diese Konten Zugriff auf die SPN-Daten des Computers haben. Wenn der Dienst unter einem anderen Konto ausgeführt wird, generiert Windows Communication \<Foundation (WCF) einen UPN in Form von *username*>@<*domainName*`>`. Die Kerberos-Authentifizierung erfordert nämlich, dass für den Client ein UPN oder SPN zum Authentifizieren des Dienstes bereitgestellt wird.  
  
 Sie können auch das [Setspn-Tool](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)?redirectedfrom=MSDN) verwenden, um einen zusätzlichen SPN mit dem Konto eines Dienstes in einer Domäne zu registrieren. Sie können dann den SPN als die Identität des Dienstes verwenden. Weitere Informationen zum Tool finden Sie unter [Setspn-Übersicht](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).  
  
> [!NOTE]
> Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Dienstes Zugriff auf den bei der Active Directory-Domäne registrierten SPN haben. Dazu stehen Ihnen folgende Möglichkeiten zur Verfügung:  
  
- Verwenden Sie das NetworkService- oder das LocalSystem-Konto, um den Dienst auszuführen. Da diese Konten Zugriff auf den Computer-SPN haben, der eingerichtet wird, wenn der Computer der Active Directory-Domäne beitritt, generiert WCF automatisch das richtige SPN-Element innerhalb des Dienstendpunkts in den Metadaten des Diensts (WSDL).  
  
- Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen. Erstellen Sie in diesem Fall mit dem Tool Setspn.exe einen SPN für dieses Domänenkonto. Nachdem Sie den SPN für das Konto des Diensts erstellt haben, konfigurieren Sie WCF so, dass dieser SPN über seine Metadaten (WSDL) auf den Clients des Dienstes veröffentlicht wird. Legen Sie dazu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.  
  
 Weitere Informationen zu SPNs, dem Kerberos-Protokoll und Active Directory finden Sie unter [Kerberos Technical Supplement für Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)).  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>Wenn SPN oder UPN der leeren Zeichenfolge entspricht  
 Das Festlegen von SPN oder UPN gleich einer leeren Zeichenfolge führt abhängig von der Sicherheitsebene und dem verwendeten Authentifizierungsmodus zu verschiedenen Ergebnissen:  
  
- Wenn Sie Sicherheit auf Transportebene verwenden, wird die NT LanMan (NTLM)-Authentifizierung ausgewählt.  
  
- Wenn Sie Sicherheit auf Nachrichtenebene verwenden, schlägt die Authentifizierung abhängig vom Authentifizierungsmodus möglicherweise fehl:  
  
- Wenn Sie den `spnego`-Modus verwenden und das `AllowNtlm`-Attribut auf `false` festgelegt ist, schlägt die Authentifizierung fehl.  
  
- Verwenden Sie den `spnego`-Modus verwenden und ist das `AllowNtlm`-Attribut auf `true` festgelegt, schlägt die Authentifizierung fehl, wenn der UPN leer ist; sie ist jedoch erfolgreich, wenn der SPN leer ist.  
  
- Wenn Sie Kerberos direkt (wird auch als "One-Shot" bezeichnet) verwenden, schlägt die Authentifizierung fehl.  
  
### <a name="using-the-identity-element-in-configuration"></a>Verwenden \<der Identität> Element in der Konfiguration  
 Wenn Sie den Clientanmeldeinformationstyp in der zuvor gezeigten Bindung zu Certificate ändern, enthält die generierte WSDL ein serialisiertes Base64-X.509-Zertifikat als Identitätswert, wie im folgenden Code gezeigt. Dies ist der Standard für alle Clientanmeldeinformationstypen außer Windows.  

 Sie können den Wert der Standarddienstidentität oder den Typ der `identity` Identität ändern, indem Sie das <>-Element in der Konfiguration verwenden oder die Identität im Code festlegen. Der folgende Konfigurationscode legt eine DNS-Identität (Domain Name System) mit dem Wert `contoso.com` fest.  

### <a name="setting-identity-programmatically"></a>Programmgesteuertes Festlegen der Identität  
 Ihr Dienst muss keine explizite Identität angeben, da WCF sie automatisch bestimmt. WCF ermöglicht es Ihnen jedoch, bei Bedarf eine Identität auf einem Endpunkt anzugeben. Mit dem folgenden Code wird ein neuer Dienstendpunkt mit einer bestimmten DNS-Identität hinzugefügt.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung](how-to-create-a-custom-client-identity-verifier.md)
- [Dienstidentität und Authentifizierung](../feature-details/service-identity-and-authentication.md)
