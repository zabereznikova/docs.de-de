---
title: 'Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: 1a8d99e5d2bd21a74318718f43b5d1c091ed073e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047541"
---
# <a name="how-to-set-a-max-clock-skew"></a>Vorgehensweise: Festlegen der maximalen Zeitdehnung (Uhrabweichung)
Zeitkritische Funktionen können behindert werden, wenn zwei Computer unterschiedliche Uhreinstellungen aufweisen. Um diese Gefahr zu umgehen, können Sie für die `MaxClockSkew`-Eigenschaft einen <xref:System.TimeSpan>-Wert festlegen. Diese Eigenschaft ist für zwei Klassen verfügbar:  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  Wichtig für eine sichere Konversation müssen Änderungen an der `MaxClockSkew` Eigenschaft muss vorgenommen werden, wenn der Dienst oder Client das Bootstrapping durchgeführt wird. Zu diesem Zweck müssen Sie die Eigenschaft festlegen, auf die <xref:System.ServiceModel.Channels.SecurityBindingElement> zurückgegebenes der <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.  
  
 Um die Eigenschaft bei einer der vom System bereitgestellten Bindungen zu ändern, suchen Sie das Sicherheitsbindungselement in der Bindungsauflistung und legen für die `MaxClockSkew`-Eigenschaft einen neuen Wert fest. Von <xref:System.ServiceModel.Channels.SecurityBindingElement> werden zwei Klassen abgeleitet: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Wenn Sie die Sicherheitsbindung aus der Auflistung abrufen, müssen Sie eine Umwandlung in einen dieser Typen durchführen, damit die `MaxClockSkew`-Eigenschaft richtig festgelegt werden kann. Im folgenden Beispiel wird eine <xref:System.ServiceModel.WSHttpBinding> verwendet, die die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Klasse nutzt. Eine Liste, der angibt, welche Art von Sicherheit Bindung in den einzelnen vom System bereitgestellten Bindungen verwendet, finden Sie unter [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>So erstellen Sie eine benutzerdefinierte Bindung mit einem neuen Zeitdehnungswert im Code  
  
1. > [!WARNING]
    >  Fügen Sie Verweise auf die folgenden Namespaces in Ihrem Code beachten: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, und <xref:System.ServiceModel.Security.Tokens>.  
  
     Erstellen Sie eine Instanz einer <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie als Sicherheitsmodus <xref:System.ServiceModel.SecurityMode.Message> fest.  
  
2. Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse durch Aufruf der <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>-Methode.  
  
3. Suchen Sie mit der <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>-Methode der <xref:System.ServiceModel.Channels.BindingElementCollection>-Klasse nach dem Sicherheitsbindungselement.  
  
4. Bei Verwendung der <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A>-Methode führen Sie eine Umwandlung in den tatsächlichen Typ durch. Im folgenden Beispiel wird eine Umwandlung in den <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Typ vorgenommen.  
  
5. Legen Sie für das Sicherheitsbindungselement die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A>-Eigenschaft fest.  
  
6. Erstellen Sie einen <xref:System.ServiceModel.ServiceHost> mit geeignetem Diensttyp und entsprechender Basisadresse.  
  
7. Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Endpunkt hinzu, und nehmen Sie die <xref:System.ServiceModel.Channels.CustomBinding> auf.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a>So legen Sie MaxClockSkew in der Konfiguration fest  
  
1. Erstellen Sie eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Elementabschnitt.  
  
2. Erstellen Sie eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element, und legen die `name` -Attribut auf einen geeigneten Wert. Im folgenden Beispiel wird das Attribut auf den Wert `MaxClockSkewBinding` festgelegt.  
  
3. Fügen Sie ein Codierungselement hinzu. Im folgenden Beispiel wird eine [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
4. Hinzufügen einer [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, und legen die `authenticationMode` -Attribut auf einen geeigneten Wert fest. Im folgenden Beispiel wird das Attribut auf `Kerberos` festgelegt, um anzugeben, dass der Dienst die Windows-Authentifizierung verwendet.  
  
5. Hinzufügen einer [ \<LocalServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) und legen Sie die `maxClockSkew` -Attribut auf einen Wert in Form von `"##:##:##"`. Im folgenden Beispiel werden sieben Minuten eingestellt. Fügen Sie optional eine [ \<LocalServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) und legen Sie die `maxClockSkew` -Attribut auf einen geeigneten Wert fest.  
  
6. Fügen Sie ein Transportelement hinzu. Im folgenden Beispiel wird ein [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
7. Für eine sichere Konversation müssen die Sicherheitseinstellungen beim Bootstrap im auftreten, müssen die [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
