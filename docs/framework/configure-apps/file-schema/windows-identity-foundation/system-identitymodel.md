---
title: '&lt;system.identityModel&gt;'
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6faeadc9fcdffc8c8aa14fdcc744896b45a941f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755252"
---
# <a name="ltsystemidentitymodelgt"></a>&lt;system.identityModel&gt;
Ermöglicht die Konfiguration für Windows Identity Foundation (WIF)-Optionen in Anwendungen zu aktivieren.  
  
 \<system.identityModel>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<configuration>`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Hinzufügen einer `<system.identityModel>` Abschnitt der Konfigurationsdatei so konfigurieren Sie einen Dienst oder Anwendung für die Verwendung von Windows Identity Foundation (WIF). Die `<system.identityModel>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Hinzufügen einer `<system.identityModel>` Abschnitt aus, um eine Konfigurationsdatei. Sie müssen zunächst Abschnitt und der Namespace der Deklaration der Konfiguration unter Hinzufügen der `<configSections>` Element. Hinzufügen der `<system.IdentityModel>` Element zu Ihrer Konfigurationsdatei, ein oder mehrere Identity-Konfigurationen an.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
