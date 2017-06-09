---
title: "&lt;securityTokenHandlers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;securityTokenHandlers&gt;
Gibt eine Auflistung von Sicherheitstokenhandler, die mit dem Endpunkt registriert sind.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|name|Gibt den Namen einer Tokenhandler\-Auflistung.  Die einzigen Werte, die vom Framework anerkannt sind "ActAs" und "OnBehalfOf".  Wenn Tokenhandler Sammlungen mit einem dieser Namen angegeben sind, wird die Auflistung verwendet werden, bei der Verarbeitung von ActAs oder OnBehalfOf bzw. Token.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Der Tokenhandler\-Auflistung hinzugefügt einen Sicherheits\-token\-Handler.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Löscht alle Sicherheitstokenhandler aus der Tokenhandler\-Auflistung.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Entfernt ein Tokenhandler Sicherheit aus der Tokenhandler\-Auflistung.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für die Auflistung der Tokenhandler.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die von Service\-Level\-Identitätseinstellungen.|  
  
## Hinweise  
 Sie können eine oder mehrere benannte Auflistungen von Sicherheitstokenhandler in einer Service\-Konfiguration angeben.  Können Sie einen Namen für eine Auflistung mithilfe der `name` Attribut.  Nur Namen, die das Framework verarbeitet werden "ActAs" und "OnBehalfOf".  Wenn diese Auflistungen Handler vorhanden sind, sie dienen von einem Security token Service \(STS\) anstelle der Standardhandler bei der Verarbeitung von `ActAs` und `OnBehalfOf` Token.  
  
 Die Auflistung wird standardmäßig mit den folgenden Handler gefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.  Sie können die Auflistung ändern, indem Sie mit der `<add>`, `<remove>`, und `<clear>` Elemente.  Sie müssen sicherstellen, dass nur ein einzelnen Handler keinen bestimmten Typ in der Auflistung vorhanden ist.  Beispielsweise, wenn Sie einen Ereignishandler aus Ableiten der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse entweder Ihre Ereignishandler oder die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> in einer einzelnen Auflistung, aber nicht beide konfiguriert werden kann.  
  
 Verwendung der `<securityTokenHandlerConfiguration>` Element, um Konfigurationseinstellungen für die Handler in der Auflistung anzugeben.  Durch dieses Element angegebenen Einstellungen zu überschreiben festgelegten Einstellungen auf den Dienst über die [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.  Einige Handler \(einschließlich einige der integrierten Ereignishandler\-Typen\) können zusätzliche Konfiguration über ein untergeordnetes Element des unterstützen die `<add>` Element.  Einstellungen auf einen Handler haben Vorrang vor entsprechende Einstellungen für die Sammlung oder den Dienst.