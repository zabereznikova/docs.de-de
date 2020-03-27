---
title: 'Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
ms.openlocfilehash: ddd9f03e26f7a8345f1070715e4877c533c361fb
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345265"
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a>Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen

In diesem Thema wird gezeigt, wie benutzerdefinierte Client- und Dienstanmeldeinformationen implementiert und benutzerdefinierte Anmeldeinformationen aus Anwendungscode genutzt werden.

## <a name="credentials-extensibility-classes"></a>Erweiterbarkeitsklassen für Anmeldeinformationen

Die <xref:System.ServiceModel.Description.ClientCredentials> <xref:System.ServiceModel.Description.ServiceCredentials> und-Klassen sind die wichtigsten Einstiegspunkte für die Windows Communication Foundation (WCF)-Sicherheitserweiterbarkeit. Diese Anmeldeinformationsklassen stellen die APIs bereit, die es dem Anmeldecode ermöglichen, Anmeldeinformationen einzurichten und Anmeldeinformationstypen in Sicherheitstoken zu konvertieren. (*Sicherheitstoken* sind das Formular, das zum Übertragen von Anmeldeinformationen in SOAP-Nachrichten verwendet wird.) Die Verantwortlichkeiten dieser Anmeldeinformationsklassen können in zwei Bereiche unterteilt werden:

- Bereitstellung der APIs für Anwendungen zur Einrichtung von Anmeldeinformationen.

- Funktion als Factory für <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Implementierungen.

Die in WCF bereitgestellten Standardimplementierungen unterstützen die vom System bereitgestellten Anmeldeinformationstypen und erstellen einen Sicherheitstoken-Manager, der in der Lage ist, diese Anmeldeinformationstypen zu verarbeiten.

## <a name="reasons-to-customize"></a>Gründe für eine Anpassung

Es gibt mehrere Gründe für die Anpassung von Client- oder Dienstanmeldeinformationsklassen. An erster Stelle steht die Anforderung, das standardmäßige WCF-Sicherheitsverhalten in Bezug auf die Verarbeitung vom System bereitgestellter Anmeldeinformationstypen zu ändern, insbesondere aus den folgenden Gründen:

- Änderungen, die mit anderen Erweiterbarkeitspunkten nicht möglich sind.

- Hinzufügen neuer Anmeldeinformationstypen.

- Hinzufügen neuer benutzerdefinierter Typen von Sicherheitstoken.

Dieses Thema beschreibt, wie benutzerdefinierte Client- und Dienstanmeldeinformationen implementiert und aus Anwendungscode genutzt werden.

## <a name="first-in-a-series"></a>Zuerst

Das Erstellen einer benutzerdefinierten Anmeldeinformationsklasse ist nur der erste Schritt, da der Grund für das Anpassen von Anmeldeinformationen darin besteht, das WCF-Verhalten in Bezug auf die Bereitstellung von Anmeldeinformationen, die Serialisierung von Sicherheitstoken oder die Authentifizierung zu ändern. Andere Themen in diesem Abschnitt beschreiben, wie benutzerdefinierte Serialisierungsprogramme und Authentifizierer erstellt werden. In diesem Zusammenhang ist die Erstellung benutzerdefinierter Anmeldeinformationsklassen das erste Thema in der Reihe. Nachfolgende Aktionen (Erstellung von benutzerdefinierten Serialisierungsprogrammen und Authentifizierern) können nur durchgeführt werden, nachdem benutzerdefinierte Anmeldeinformationen erstellt wurden. Weitere Themen, die auf diesem Thema aufbauen:

- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md)

- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](how-to-create-a-custom-security-token-authenticator.md)

- [Gewusst wie: Erstellen eines benutzerdefinierten Tokens](how-to-create-a-custom-token.md).

## <a name="procedures"></a>Verfahren

#### <a name="to-implement-custom-client-credentials"></a>So implementieren Sie benutzerdefinierte Clientanmeldeinformationen

1. Definieren Sie eine neue von der <xref:System.ServiceModel.Description.ClientCredentials>-Klasse abgeleitete Klasse.

2. Optional. Fügen Sie Methoden oder Eigenschaften für neue Anmeldeinformationstypen hinzu. Wenn Sie keine neuen Anmeldeinformationstypen hinzufügen, können Sie diesen Schritt überspringen. Im folgenden Beispiel wird eine `CreditCardNumber`-Eigenschaft hinzugefügt.

3. Überschreiben Sie die <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> -Methode. Diese Methode wird automatisch von der WCF-Sicherheitsinfrastruktur aufgerufen, wenn die benutzerdefinierten Clientanmeldeinformationen verwendet werden. Diese Methode ist für die Erstellung und die Rückgabe einer Implementierungsinstanz der <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse verantwortlich.

    > [!IMPORTANT]
    > Wichtig: Beachten Sie, dass die <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A>-Methode überschrieben wird, um einen benutzerdefinierten Sicherheitstokenmanager zu erstellen. Der vom <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> abgeleitete Sicherheitstokenmanager muss einen benutzerdefinierten Sicherheitstokenanbieter zurückgeben, der vom <xref:System.IdentityModel.Selectors.SecurityTokenProvider> abgeleitet wurde, um das eigentliche Sicherheitstoken zu erstellen. Befolgen Sie nicht diese Vorgehensweise zur Erstellung von Sicherheitstokens, funktioniert die Anwendung möglicherweise nicht korrekt, wenn <xref:System.ServiceModel.ChannelFactory>-Objekte zwischengespeichert werden, was das standardmäßige Verhalten von WCF-Clientproxys ist. Dies kann ggf. einen Angriff durch Rechteerweiterung zur Folge haben. Das benutzerdefinierte Anmeldedatenobjekt wird als Teil des <xref:System.ServiceModel.ChannelFactory>-Objekts zwischengespeichert. Der benutzerdefinierte <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird jedoch bei jedem Aufruf erstellt. So lange die Tokenerstellungslogik also im <xref:System.IdentityModel.Selectors.SecurityTokenManager> platziert wird, wird die Sicherheitsbedrohung abgewehrt.

4. Überschreiben Sie die <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> -Methode.

    [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
    [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]

#### <a name="to-implement-a-custom-client-security-token-manager"></a>So implementieren Sie einen benutzerdefinierten Clientsicherheitstoken-Manager

1. Definieren Sie eine neue Klasse, die von <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> abgeleitet ist.

2. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>-Methode, wenn eine benutzerdefinierte <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Implementierung erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstokenanbietern finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md).

3. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29>-Methode, wenn eine benutzerdefinierte <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>-Implementierung erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstokenauthentifikatoren finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifikators](how-to-create-a-custom-security-token-authenticator.md).

4. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A>-Methode, wenn ein benutzerdefinierter <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstoken und benutzerdefinierten Sicherheitstokenserialisierern finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Tokens](how-to-create-a-custom-token.md).

    [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
    [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]

#### <a name="to-use-a-custom-client-credentials-from-application-code"></a>So verwenden Sie benutzerdefinierte Clientanmeldeinformationen aus Anwendungscode

1. Erstellen Sie entweder eine Instanz des generierten Clients, die die Dienstschnittstelle darstellt, oder erstellen Sie eine Instanz der <xref:System.ServiceModel.ChannelFactory>, die auf den Dienst verweist, mit dem Sie kommunizieren möchten.

2. Entfernen Sie das vom System bereitgestellte Clientanmeldeinformationsverhalten aus der <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>-Sammlung, auf die von der <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>-Eigenschaft aus zugegriffen werden kann.

3. Erstellen Sie eine neue Instanz einer benutzerdefinierten Clientanmeldeinformationsklasse, und fügen Sie diese zur <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>-Sammlung hinzu, auf die über die <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>-Eigenschaft zugegriffen werden kann.

    [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
    [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]

Die oben beschriebene Prozedur zeigt, wie Clientanmeldeinformationen aus dem Anwendungscode genutzt werden können. WCF-Anmeldeinformationen können auch mithilfe der Anwendungskonfigurationsdatei konfiguriert werden. Die Nutzung der Anwendungskonfiguration ist in vielen Fällen einer harten Codierung vorzuziehen, da hier eine Änderung der Anwendungsparameter ermöglicht wird, ohne dass ein Ändern der Quelle oder eine Neukompilierung und Neubereitstellung erforderlich sind.

Die nächste Prozedur beschreibt, wie eine Unterstützung für die Konfiguration von benutzerdefinierten Anmeldeinformationen erstellt wird.

#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a>Erstellen eines Konfigurationshandlers für benutzerdefinierte Clientanmeldeinformationen

1. Definieren Sie eine neue Klasse, die von <xref:System.ServiceModel.Configuration.ClientCredentialsElement> abgeleitet ist.

2. Optional. Fügen Sie Eigenschaften für alle zusätzlichen Konfigurationsparameter hinzu, die Sie durch Anwendungskonfiguration verfügbar machen möchten. Im unten angegebenen Beispiel wird eine Eigenschaft mit dem Namen `CreditCardNumber` hinzugefügt.

3. Überschreiben Sie die <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A>-Eigenschaft, um den Typ der benutzerdefinierten Clienanmeldeinformationsklasse zurückzugeben, der mithilfe des Konfigurationselements erstellt wurde.

4. Überschreiben Sie die <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> -Methode. Die Methode ist basierend auf den von der Konfigurationsdatei geladenen Einstellungen für die Erstellung und Rückgabe einer Instanz der benutzerdefinierten Anmeldeinformationsklasse verantwortlich. Rufen Sie die grundlegende <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29>-Methode von dieser Methode auf, um die vom System bereitgestellten Anmeldeinformationseinstellungen abzurufen, die in Ihre benutzerdefinierte Clientanmeldeinformationsinstanz geladen sind.

5. Optional. Wenn Sie in Schritt 2 zusätzliche Eigenschaften hinzugefügt haben, müssen Sie die <xref:System.Configuration.ConfigurationElement.Properties%2A>-Eigenschaft zum Registrieren Ihrer zusätzlichen Konfigurationseinstellungen überschreiben, damit der Konfigurationsframework diese erkennt. Kombinieren Sie Ihre Eigenschaften mit den grundlegenden Klasseneigenschaften, um zu ermöglichen, dass die vom System bereitgestellten Einstellungen über das Konfigurationselement dieser benutzerdefinierten Clientanmeldeinformationen konfiguriert werden können.

    [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
    [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]

Sobald Sie über die Konfigurationshandlerklasse verfügen, kann sie in das WCF-Konfigurationsframework integriert werden. Dies ermöglicht die Verwendung benutzerdefinierter Clientanmeldeinformationen in den Clientendpunktverhaltenselementen, wie in der nächsten Prozedur gezeigt wird.

#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a>Registrieren und Verwenden eines benutzerdefinierten Clientanmeldeinformationen-Konfigurationshandlers in der Anwendungskonfiguration

1. Fügen Sie `extensions` der Konfigurationsdatei `behaviorExtensions` ein <>-Element und ein <>-Element hinzu.

2. Fügen Sie `add` dem <`behaviorExtensions`>-Element ein `name` <>-Element hinzu, und legen Sie das Attribut auf einen geeigneten Wert fest.

3. Legen Sie das `type`-Attribut auf den vollqualifizierten Typnamen fest. Binden Sie ebenfalls den Assemblynamen und andere Assemblyattribute ein.

    ```xml
    <system.serviceModel>
      <extensions>
        <behaviorExtensions>
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </behaviorExtensions>
      </extensions>
    </system.serviceModel>
    ```

4. Nach der Registrierung des Konfigurationshandlers kann das benutzerdefinierte Anmeldeinformationselement in derselben `clientCredentials` Konfigurationsdatei anstelle der vom System bereitgestellten <> Element verwendet werden. Sie können sowohl die vom System bereitgestellten Eigenschaften als auch neue Eigenschaften verwenden, die Sie in Ihre Konfigurationshandlerimplementierung eingefügt haben. Im folgenden Beispiel wird der Wert einer benutzerdefinierten Eigenschaft mithilfe des `creditCardNumber`-Attributs eingerichtet.

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="myClientCredentialsBehavior">
          <myClientCredentials creditCardNumber="123-123-123"/>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

#### <a name="to-implement-custom-service-credentials"></a>So implementieren Sie benutzerdefinierte Dienstanmeldeinformationen

1. Definieren Sie eine neue Klasse, die von <xref:System.ServiceModel.Description.ServiceCredentials> abgeleitet ist.

2. Optional. Fügen Sie neue Eigenschaften hinzu, um APIs für neue Werte für die Anmeldeinformationen bereitzustellen, die hinzugefügt werden. Wenn Sie keine neuen Anmeldeinformationswerte hinzufügen, können Sie diesen Schritt überspringen. Im folgenden Beispiel wird die `AdditionalCertificate`-Eigenschaft hinzugefügt.

3. Überschreiben Sie die <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> -Methode. Diese Methode wird automatisch von der WCF-Infrastruktur aufgerufen, wenn die benutzerdefinierten Clientanmeldeinformationen verwendet werden. Die Methode ist für die Erstellung und die Rückgabe einer Implementierungsinstanz der <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse verantwortlich (wie in der nächsten Prozedur beschrieben).

4. Optional. Überschreiben Sie die <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> -Methode. Dies ist nur erforderlich, wenn neue Eigenschaften oder interne Felder zur benutzerdefinierten Clientanmeldeinformationsimplementierung hinzugefügt werden.

    [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
    [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]

#### <a name="to-implement-a-custom-service-security-token-manager"></a>So implementieren Sie einen benutzerdefinierten Dienstsicherheitstoken-Manager

1. Definieren Sie eine neue von der <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>-Klasse abgeleitete Klasse.

2. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A>-Methode, wenn eine benutzerdefinierte <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Implementierung erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstokenanbietern finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md).

3. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>-Methode, wenn eine benutzerdefinierte <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>-Implementierung erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstokenauthentifikatoren finden Sie unter Gewusst wie: Erstellen eines Themas für [benutzerdefinierte Sicherheitstokenauthentifikatoren.](how-to-create-a-custom-security-token-authenticator.md)

4. Optional. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29>-Methode, wenn ein benutzerdefinierter <xref:System.IdentityModel.Selectors.SecurityTokenSerializer> erstellt werden muss. Weitere Informationen zu benutzerdefinierten Sicherheitstoken und benutzerdefinierten Sicherheitstokenserialisierern finden Sie unter [Gewusst wie: Erstellen eines benutzerdefinierten Tokens](how-to-create-a-custom-token.md).

    [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
    [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]

#### <a name="to-use-custom-service-credentials-from-application-code"></a>So verwenden Sie benutzerdefinierte Dienstanmeldeinformationen aus Anwendungscode

1. Erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>.

2. Entfernen Sie das vom System bereitgestellte Dienstanmeldeinformationsverhalten aus der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Sammlung.

3. Erstellen Sie eine neue Instanz der benutzerdefinierten Dienstanmeldeinformationsklasse, und fügen Sie diese der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>-Sammlung hinzu.

    [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
    [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]

Fügen Sie Unterstützung für die Konfiguration mithilfe`To create a configuration handler for custom client credentials`der`To register and use a custom client credentials configuration handler in the application configuration`zuvor beschriebenen Schritte in den Prozeduren " und " hinzu. Der einzige Unterschied besteht <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> darin, <xref:System.ServiceModel.Configuration.ClientCredentialsElement> die Klasse anstelle der Klasse als Basisklasse für den Konfigurationshandler zu verwenden. Das benutzerdefinierte Dienstanmeldeinformationselement kann immer verwendet werden, wenn das vom System bereitgestellte `<serviceCredentials>`-Element genutzt wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Security.SecurityCredentialsManager>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](how-to-create-a-custom-security-token-authenticator.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](how-to-create-a-custom-token.md)
