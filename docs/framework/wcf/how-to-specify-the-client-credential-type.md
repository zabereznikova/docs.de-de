---
title: "Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Sicherheitsanmeldeinformationen, Hinzufügen zu SOAP-Nachrichten"
  - "WCF, Sicherheit"
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen
Nach dem Festlegen eines Sicherheitsmodus \(entweder Transport oder Nachricht\) haben Sie die Möglichkeit, den Typ der Clientanmeldeinformationen anzugeben.Diese Eigenschaft spezifiziert, welchen Anmeldeinformationstyp der Client dem Dienst zur Authentifizierung angeben muss.[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Festlegen des Sicherheitsmodus \(ein notwendiger Schritt vor dem Festlegen des Typs der Clientanmeldeinformationen\) finden Sie unter [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
### So legen Sie den Clientanmeldeinformationstyp in Code fest  
  
1.  Erstellen Sie eine Instanz der Bindung, die der Dienst nutzt.In diesem Beispiel wird die <xref:System.ServiceModel.WSHttpBinding>\-Bindung verwendet.  
  
2.  Legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>\-Eigenschaft auf einen geeigneten Wert fest.In diesem Beispiel wird der Nachrichtenmodus verwendet.  
  
3.  Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>\-Eigenschaft auf einen geeigneten Wert fest.In diesem Beispiel wird die Verwendung der Windows\-Authentifizierung \(<xref:System.ServiceModel.MessageCredentialType>\) festgelegt.  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### So legen Sie den Clientanmeldeinformationstyp in der Konfiguration fest  
  
1.  Fügen Sie ein [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Element zur Konfigurationsdatei hinzu.  
  
2.  Fügen Sie als untergeordnetes Element ein [\<Bindungen\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Element hinzu.  
  
3.  Fügen Sie eine entsprechende Bindung hinzu.In diesem Beispiel wird das [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\-Element verwendet.  
  
4.  Fügen Sie ein [\<Bindung\>](../../../docs/framework/misc/binding.md)\-Element hinzu, und legen Sie das `name`\-Attribut auf einen passenden Wert fest.In diesem Beispiel wird der Name "SecureBinding" verwendet.  
  
5.  Fügen Sie eine `<security>`\-Bindung hinzu.Legen Sie für das `mode`\-Attribut einen geeigneten Wert fest.Im folgenden Beispiel wird das Attribut auf `"Message"` festgelegt.  
  
6.  Fügen Sie entweder ein `<message>``<transport>-Element oder ein` \-Element hinzu, wie vom Sicherheitsmodus bestimmt.Legen Sie für das `clientCredentialType`\-Attribut einen geeigneten Wert fest.In diesem Beispiel wird der Wert `"Windows"` verwendet.  
  
    ```  
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
  
## Siehe auch  
 [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md)   
 [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../docs/framework/wcf/how-to-set-the-security-mode.md)