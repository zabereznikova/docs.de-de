---
title: 'Vorgehensweise: Einrichten einer Signaturbestätigung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 56e8720a6130d2908fbfb83bd243a54fae9a2406
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972925"
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Vorgehensweise: Einrichten einer Signaturbestätigung
*Signaturbestätigung* ist ein Mechanismus für einen nachrichteninitiator, um sicherzustellen, dass eine empfangene Antwort als Antwort auf die ursprüngliche Nachricht des Absenders generiert wurde. Die Signaturbestätigung wird in der WS-Sicherheit 1.1-Spezifikation definiert. Wenn ein Endpunkt WS-Sicherheit 1.0 unterstützt, können Sie keine Signaturbestätigung verwenden.  
  
 In den folgenden Verfahren wird beschrieben, wie die Signaturbestätigung mit <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> aktiviert wird. Sie können das gleiche Verfahren mit <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwenden. Das Verfahren baut auf die grundlegenden Schritte finden Sie im [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-code"></a>So aktivieren Sie die Signaturbestätigung in Code  
  
1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse.  
  
2. Erstellen Sie eine Instanz von der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> Klasse.  
  
3. Legen Sie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> auf `true` fest  
  
4. Fügen Sie der Bindungsauflistung das Sicherheitselement hinzu.  
  
5. Erstellen Sie eine benutzerdefinierte Bindung gemäß [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a>So aktivieren Sie die Signaturbestätigung in der Konfiguration  
  
1. Fügen Sie dem `<customBinding>``<bindings>`-Abschnitt der Konfigurationsdatei ein -Element hinzu.  
  
2. Fügen Sie ein `<binding>`-Element hinzu, und legen Sie das Namensattribut auf einen passenden Wert fest.  
  
3. Fügen Sie ein entsprechendes Codierungselement hinzu. Im folgenden Beispiel wird ein `<TextMessageEncoding>`-Element hinzugefügt.  
  
4. Hinzufügen einer `<security>` untergeordnete Element, und legen die `requireSignatureConfirmation` -Attribut `true`.  
  
5. Dies ist optional. Um signaturbestätigung während des Bootstraps aktivieren möchten, fügen einen [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) untergeordneten-Element, und legen die `equireSignatureConfirmation` Attribut `true`.  
  
6. Fügen Sie ein entsprechendes Transportelement hinzu. Im folgenden Beispiel wird ein [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt eine Instanz von <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und legt die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>-Eigenschaft auf `true` fest. Beachten Sie, dass in diesem Beispiel das im vorangehenden Beispiel gezeigte `<secureConversationBootstrap>`-Element nicht verwendet wird. In diesem Beispiel wird die Signaturbestätigung veranschaulicht, wenn ein Windows-(Kerberos-Protokoll)-Token verwendet wird. In diesem Fall wird die Signatur des Clients in allen Antworten vom Dienst zurückgegeben und vom Client bestätigt.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
