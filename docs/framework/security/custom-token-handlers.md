---
title: Benutzerdefinierte Tokenhandler
ms.date: 03/30/2017
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
author: BrucePerlerMS
ms.openlocfilehash: ccf794b4c229bbc9b40ae7ec2fd649825122cecf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040556"
---
# <a name="custom-token-handlers"></a>Benutzerdefinierte Tokenhandler
In diesem Thema werden Tokenhandler in WIF und ihre Verwendung zur Verarbeitung von Token erläutert. Das Thema behandelt auch die Vorgehensweise zum Erstellen von benutzerdefinierten Tokenhandlern für Tokentypen, die nicht standardmäßig in WIF unterstützt werden.  
  
## <a name="introduction-to-token-handlers-in-wif"></a>Einführung in Tokenhandler in WIF  
 WIF verwendet Sicherheitstokenhandler zum Erstellen, Lesen, Schreiben und Überprüfen von Token für eine Anwendung der vertrauenden Seite (Relying Party, RP) oder einen Sicherheitstokendienst (Security Token Service, STS). Tokenhandler sind Erweiterungspunkte, um der WIF-Pipeline einen benutzerdefinierten Tokenhandler hinzuzufügen oder die Tokenverwaltung eines vorhandenen Tokenhandlers anzupassen. WIF stellt neun integrierte Sicherheitstokenhandler bereit, deren Funktionen nach Bedarf geändert oder vollständig überschrieben werden können.  
  
## <a name="built-in-security-token-handlers-in-wif"></a>Integrierte Sicherheitstokenhandler in WIF  
 WIF 4.5 beinhaltet neun Klassen für Sicherheitstokenhandler, die von der abstrakten Basisklasse <xref:System.IdentityModel.Tokens.SecurityTokenHandler> abgeleitet werden:  
  
- <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
- <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## <a name="adding-a-custom-token-handler"></a>Hinzufügen eines benutzerdefinierten Tokenhandlers  
 Einige Tokentypen, wie z.B. einfache Webtoken (Simple Web Tokens, SWT) und JSON-Webtoken (JWT), verfügen über keine integrierten WIF-Sicherheitstokenhandler. Bei diesen Tokentypen und bei Typen, die nicht über einen integrierten Handler verfügen, müssen Sie folgendermaßen vorgehen, um einen benutzerdefinierten Tokenhandler zu erstellen.  
  
#### <a name="adding-a-custom-token-handler"></a>Hinzufügen eines benutzerdefinierten Tokenhandlers  
  
1. Erstellen Sie eine neue Klasse, die von <xref:System.IdentityModel.Tokens.SecurityTokenHandler> abgeleitet wird.  
  
2. Überschreiben Sie die folgenden Methoden, und stellen Sie Ihre eigene Implementierung bereit:  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    - <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3. Fügen Sie im **\<system.identityModel>** -Abschnitt für WIF in der Datei *Web.config* oder der Datei *App.config* dem neuen benutzerdefinierten Tokenhandler einen Verweis hinzu. Das folgende Konfigurationsmarkup gibt z.B. einen neuen Tokenhandler mit dem Namen **MyCustomTokenHandler** an, der sich im Namespace **CustomToken** befindet.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Beachten Sie, dass Sie beim Bereitstellen Ihres eigenen Tokenhandlers zur Behandlung eines Tokentyps mit integriertem Tokenhandler ein **\<remove>** -Element hinzufügen müssen, um den Standardhandler zu löschen und dafür den benutzerdefinierten Handler zu verwenden. Die folgende Konfiguration ersetzt beispielsweise den standardmäßigen <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> durch den benutzerdefinierten Tokenhandler:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789" />  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```
