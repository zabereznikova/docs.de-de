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
ms.openlocfilehash: 9423922753efee7aac32e430f97307c715e43464
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586916"
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Vorgehensweise: Einrichten einer Signaturbestätigung

*Signatur Bestätigung* ist ein Mechanismus für einen Nachrichten Initiator, mit dem sichergestellt wird, dass eine empfangene Antwort als Antwort auf die ursprüngliche Nachricht des Absenders generiert wurde. Die Signaturbestätigung wird in der WS-Sicherheit 1.1-Spezifikation definiert. Wenn ein Endpunkt WS-Sicherheit 1.0 unterstützt, können Sie keine Signaturbestätigung verwenden.

In den folgenden Verfahren wird beschrieben, wie die Signaturbestätigung mit <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> aktiviert wird. Sie können das gleiche Verfahren mit <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwenden. Die Prozedur baut auf den grundlegenden Schritten auf, die unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)beschrieben werden.

### <a name="to-enable-signature-confirmation-in-code"></a>So aktivieren Sie die Signaturbestätigung in Code

1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse.

2. Erstellen Sie eine Instanz der- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> Klasse.

3. Legen Sie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> auf `true` fest.

4. Fügen Sie der Bindungsauflistung das Sicherheitselement hinzu.

5. Erstellen Sie eine benutzerdefinierte Bindung, wie in Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)angegeben.

### <a name="to-enable-signature-confirmation-in-configuration"></a>So aktivieren Sie die Signaturbestätigung in der Konfiguration

1. Fügen Sie dem -Abschnitt der Konfigurationsdatei ein -Element hinzu.

2. Fügen Sie ein `<binding>`-Element hinzu, und legen Sie das Namensattribut auf einen passenden Wert fest.

3. Fügen Sie ein entsprechendes Codierungselement hinzu. Im folgenden Beispiel wird ein `<TextMessageEncoding>`-Element hinzugefügt.

4. Fügen Sie ein untergeordnetes `<security>``requireSignatureConfirmation` fest.

5. Optional. Fügen Sie ein untergeordnetes Element hinzu, [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) und legen Sie das- `requireSignatureConfirmation` Attribut auf fest, um die Signatur Bestätigung während des Bootstrap `true` zu aktivieren

6. Fügen Sie ein entsprechendes Transportelement hinzu. Im folgenden Beispiel wird ein hinzugefügt [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
