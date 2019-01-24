---
title: 'Vorgehensweise: Geben Sie den Typ der Clientanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: 9fe999c4ee27d4a78bfad185fa3bcc065d74708a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643377"
---
# <a name="how-to-specify-the-client-credential-type"></a>Vorgehensweise: Geben Sie den Typ der Clientanmeldeinformationen
Nach dem Festlegen eines Sicherheitsmodus (entweder Transport oder Nachricht) haben Sie die Möglichkeit, den Typ der Clientanmeldeinformationen anzugeben. Diese Eigenschaft gibt an, welchen Anmeldeinformationstyp der Client dem Dienst zur Authentifizierung bereitstellen muss. Weitere Informationen zum Festlegen des Sicherheitsmodus (ein notwendiger Schritt vor dem Festlegen des Typ der Clientanmeldeinformationen) finden Sie unter [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>So legen Sie den Clientanmeldeinformationstyp in Code fest  
  
1.  Erstellen Sie eine Instanz der Bindung, die der Dienst nutzt. In diesem Beispiel wird die <xref:System.ServiceModel.WSHttpBinding>-Bindung verwendet.  
  
2.  Legen Sie für die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft einen geeigneten Wert fest. In diesem Beispiel wird der Nachrichtenmodus verwendet.  
  
3.  Legen Sie für die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest. In diesem Beispiel wird die Verwendung der Windows-Authentifizierung (<xref:System.ServiceModel.MessageCredentialType.Windows>) festgelegt.  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>So legen Sie den Clientanmeldeinformationstyp in der Konfiguration fest  
  
1.  Hinzufügen einer [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Element der Konfigurationsdatei hinzu.  
  
2.  Hinzufügen als ein untergeordnetes Element eine [ \<Bindungen >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element.  
  
3.  Fügen Sie eine entsprechende Bindung hinzu. Dieses Beispiel verwendet die [ \<WsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.  
  
4.  Hinzufügen einer [ \<Bindung >](../../../docs/framework/misc/binding.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert. In diesem Beispiel wird der Name "SecureBinding" verwendet.  
  
5.  Fügen Sie eine `<security>`-Bindung hinzu. Legen Sie für das `mode`-Attribut einen geeigneten Wert fest. Im folgenden Beispiel wird das Attribut auf `"Message"` festgelegt.  
  
6.  Fügen Sie entweder ein `<message>`-Element oder ein`<transport>`-Element hinzu, wie vom Sicherheitsmodus bestimmt. Legen Sie für das `clientCredentialType`-Attribut einen geeigneten Wert fest. In diesem Beispiel wird `"Windows"` verwendet.  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>Siehe auch
- [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)
- [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
