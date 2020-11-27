---
title: 'Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293675"
---
# <a name="how-to-specify-the-client-credential-type"></a>Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen

Nach dem Festlegen eines Sicherheitsmodus (entweder Transport oder Nachricht) haben Sie die Möglichkeit, den Typ der Clientanmeldeinformationen anzugeben. Diese Eigenschaft gibt an, welchen Anmeldeinformationstyp der Client dem Dienst zur Authentifizierung bereitstellen muss. Weitere Informationen zum Festlegen des Sicherheitsmodus (ein notwendiger Schritt vor dem Festlegen des Client Anmelde Informations Typs) finden Sie unter Gewusst [wie: Festlegen des Sicherheitsmodus](how-to-set-the-security-mode.md).  
  
### <a name="to-set-the-client-credential-type-in-code"></a>So legen Sie den Clientanmeldeinformationstyp in Code fest  
  
1. Erstellen Sie eine Instanz der Bindung, die der Dienst nutzt. In diesem Beispiel wird die <xref:System.ServiceModel.WSHttpBinding>-Bindung verwendet.  
  
2. Legen Sie für die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft einen geeigneten Wert fest. In diesem Beispiel wird der Nachrichtenmodus verwendet.  
  
3. Legen Sie für die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest. In diesem Beispiel wird die Verwendung der Windows-Authentifizierung (<xref:System.ServiceModel.MessageCredentialType.Windows>) festgelegt.  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>So legen Sie den Clientanmeldeinformationstyp in der Konfiguration fest  
  
1. Fügen Sie [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) der Konfigurationsdatei ein-Element hinzu.  
  
2. Fügen Sie ein-Element als untergeordnetes Element hinzu [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) .  
  
3. Fügen Sie eine entsprechende Bindung hinzu. In diesem Beispiel wird das- [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) Element verwendet.  
  
4. Fügen Sie ein [\<binding>](../configure-apps/file-schema/wcf/bindings.md) -Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest In diesem Beispiel wird der Name "SecureBinding" verwendet.  
  
5. Fügen Sie eine `<security>`-Bindung hinzu. Legen Sie für das `mode`-Attribut einen geeigneten Wert fest. Im folgenden Beispiel wird das Attribut auf `"Message"` festgelegt.  
  
6. Fügen Sie entweder ein `<message>`-Element hinzu, wie vom Sicherheitsmodus bestimmt. Legen Sie für das `clientCredentialType`-Attribut einen geeigneten Wert fest. In diesem Beispiel wird `"Windows"` verwendet.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von Diensten](securing-services.md)
- [Vorgehensweise: Festlegen des Sicherheitsmodus](how-to-set-the-security-mode.md)
