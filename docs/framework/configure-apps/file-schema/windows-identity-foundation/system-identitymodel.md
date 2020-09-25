---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 216b4c73e06469d6577c61338ad1af0fdd2dc05e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185573"
---
# \<system.identityModel>

Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  

 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<configuration>`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="remarks"></a>Bemerkungen  

 Fügen Sie `<system.identityModel>` der Konfigurationsdatei einen Abschnitt hinzu, um einen Dienst oder eine Anwendung für die Verwendung von Windows Identity Foundation (WIF) zu konfigurieren. Das- `<system.identityModel>` Element wird durch die- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie einer Konfigurationsdatei ein-Abschnitt hinzugefügt wird `<system.identityModel>` . Sie müssen zunächst den Konfigurations Abschnitt und die Namespace Deklaration unter dem-Element hinzufügen `<configSections>` . Anschließend können Sie das- `<system.IdentityModel>` Element der Konfigurationsdatei hinzufügen, um eine oder mehrere Identitäts Konfigurationen anzugeben.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
