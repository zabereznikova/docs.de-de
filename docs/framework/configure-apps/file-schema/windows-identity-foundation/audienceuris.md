---
title: "&lt;audienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;audienceUris&gt;
Gibt den Satz der URIs, die zulässigen Bezeichner der relying Party \(RP\) sind.  Token werden nicht angenommen, wenn sie einen, für eine der zulässigen Zielgruppen\-URIs Bereich.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|mode|Ein <xref:System.IdentityModel.Selectors.AudienceUriMode> Wert, der angibt, ob die Publikum Beschränkung auf eine eingehende Token angewendet werden soll.  Die möglichen Werte sind "Always", "Nie" und "BearerKeyOnly".  Der Standardwert ist "Immer".  Optional.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`<add value=xs:string>`|Fügt den angegebenen URI die `value` \-Attribut auf die AudienceUris\-Auflistung.  Das `value`\-Attribut ist erforderlich.  Der URI ist Groß\-\/Kleinschreibung beachtet.|  
|`<clear>`|Löscht die Auflistung der AudienceUris.  Alle Bezeichner werden aus der Auflistung entfernt.|  
|`<remove value=xs:string>`|Entfernt den angegebenen URI die `value` \-Attribut aus der Auflistung der AudienceUris.  Das `value`\-Attribut ist erforderlich.  Der URI ist Groß\-\/Kleinschreibung beachtet.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheit Tokenhandler.|  
  
## Hinweise  
 Standardmäßig ist die Auflistung leer; Verwenden Sie `<add>`, `<clear>`, und `<remove>` Elemente die Auflistung zu ändern.  <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>und <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> verwenden die Werte im Publikum URI\-Auflistung eine konfigurieren Publikum URI\-Einschränkungen in erlaubt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekte.  
  
 Die `<audienceUris>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> Klasse.  Ein einzelner URI, der der Auflistung hinzugefügt wird dargestellt durch die <xref:System.IdentityModel.Configuration.AudienceUriElement> Klasse.  
  
> [!NOTE]
>  Die Verwendung der `<audienceUris>` Element als untergeordnetes Element von der [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber wird aus Kompatibilitätsgründen weiterhin unterstützt.  Einstellungen auf die `<securityTokenHandlerConfiguration>` Element überschreiben die auf die `<identityConfiguration>` Element.  
  
## Beispiel  
 Das folgende XML veranschaulicht die zulässigen Zielgruppen\-URIs für eine Anwendung konfigurieren.  In diesem Beispiel wird einen einzelnen URI.  Der Gültigkeitsbereich für diesen URI Token akzeptiert werden, alle anderen werden abgelehnt.  
  
```  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```