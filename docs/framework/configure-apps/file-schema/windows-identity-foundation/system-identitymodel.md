---
title: "&lt;system.identityModel&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;system.identityModel&gt;
Stellt die Konfiguration für das Aktivieren von Optionen für die Windows\-Identität\-Foundation \(WIF\) in Anwendungen.  
  
 \<system.identityModel\>  
  
## Syntax  
  
```  
<system.identityModel>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 None  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die von Service\-Level\-Identitätseinstellungen.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`<configuration>`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
  
## Hinweise  
 Hinzufügen einer `<system.identityModel>` Abschnitt der Konfigurationsdatei zum Konfigurieren eines Diensts oder einer Anwendung für die Verwendung der Windows\-Identität\-Foundation \(WIF\).  Die `<system.identityModel>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht das Hinzufügen einer `<system.identityModel>` Abschnitt einer Konfigurationsdatei.  Sie müssen zunächst die Konfiguration Konfigurationsabschnitts\- und den Vermerk nach Hinzufügen der `<configSections>` Element.  Anschließend fügen Sie können die `<system.IdentityModel>` Element der Konfigurationsdatei zu Konfigurationen für mindestens eine Identität angeben.  
  
```  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>