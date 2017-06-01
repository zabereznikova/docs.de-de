---
title: "Benutzerdefinierte Tokenhandler | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5062669f-8bfc-420a-a25d-d8ab992ab10e
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Benutzerdefinierte Tokenhandler
In diesem Thema werden Scheinhandler in WIF und wie diese verwendet werden, um Token zu verarbeiten.  Im Thema werden auch ab, was erforderlich ist, um benutzerdefinierte Scheinhandler für Tokentypen zu erstellen, die nicht standardmäßig in WIF unterstützt werden.  
  
## Einführung in den Scheinhandlern in WIF  
 WIF beruht auf Sicherheitstokenhandlern, um Token für eine Anwendung des vertrauender Seite \(RP\) oder einen Sicherheitstokendienst \(STS\) zum Erstellen, Lesen, Schreiben und zu überprüfen.  Scheinhandler sind Erweiterungspunkte, damit Sie einen benutzerdefinierten Scheinhandler in der WIF\-Pipeline hinzufügen oder die Methode anpassen, der ein vorhandener Scheinhandler Token verwaltet.  WIF stellt neun integrierte Sicherheitstokenhandler, die geändert oder vollständig überschrieben werden können, um die Funktionalität bei Bedarf zu ändern.  
  
## Integrierte Sicherheitstoken\-Handler in WIF  
 WIF 4.5 enthält neun Sicherheitstokenhandlerklassen ein, die von der abstrakten Basisklasse <xref:System.IdentityModel.Tokens.SecurityTokenHandler> berechnen:  
  
-   <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.UserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>  
  
-   <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>  
  
## Hinzufügen eines benutzerdefinierten Scheinhandlers  
 Eine Tokentypen, wie einfache Token der Internet\-Token\-\(SWT\) und JSON\-Internets \(JWT\) verfügen nicht über die integrierten Scheinhandler, die von WIF bereitgestellt werden.  Für diese Tokentypen und für andere, die keinen integrierten Handler verfügen, müssen Sie die folgenden Schritte ausführen, um einen benutzerdefinierten Scheinhandler zu erstellen.  
  
#### Hinzufügen eines benutzerdefinierten Scheinhandlers  
  
1.  Erstellen Sie eine neue Klasse, die von <xref:System.IdentityModel.Tokens.SecurityTokenHandler> abgeleitet.  
  
2.  Überschreiben Sie die folgenden Methoden und stellen Sie eine eigene Implementierung bereit:  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ReadToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanWriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.WriteToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.CanValidateToken%2A>  
  
    -   <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>  
  
3.  Fügen Sie einen Verweis auf den neuen benutzerdefinierten Scheinhandler in die Datei *Web.config* oder *App.configfile* innerhalb des **\<system.identityModel\>**\-Abschnitts hinzu, der für WIF gilt.  Beispielsweise gibt die folgende Konfigurationsmarkup einen neuen Scheinhandler an, der **MyCustomTokenHandler** genannt wird, der im **CustomToken**\-Namespace befinden.  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```  
  
     Beachten Sie, dass, wenn Sie Ihren eigenen Scheinhandler bereitstellen, um einen Tokentyp zu behandeln, der bereits einen integrierten Scheinhandler verfügt, Sie ein **\<remove\>**\-Element hinzufügen müssen, um den Standardhandler abzulegen und den benutzerdefinierten Handler stattdessen zu verwenden.  Beispielsweise ersetzt die folgende Konfiguration Standard <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> vom benutzerdefinierten Scheinhandler:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration saveBootstrapContext="true">  
            <securityTokenHandlers>  
                <remove type=”System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcdefg123456789”>  
                <add type="CustomToken.MyCustomTokenHandler, CustomToken" />  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
    ```