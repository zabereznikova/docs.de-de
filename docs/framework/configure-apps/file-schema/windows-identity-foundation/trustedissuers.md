---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251762"
---
# \<trustedIssuers>
Konfiguriert die Liste der vertrauenswürdigen Aussteller Zertifikate, die von der Konfigurations basierten Aussteller Namen Registrierung verwendet werden ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> ).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerNameRegistry>**](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trustedIssuers>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Fügt der Auflistung vertrauenswürdiger Aussteller ein Zertifikat hinzu. Das Zertifikat wird mit dem- `thumbprint` Attribut angegeben. Dieses Attribut ist erforderlich und sollte die ASN. 1-codierte Form des Zertifikat Fingerabdrucks enthalten. Das `name` -Attribut ist optional und kann verwendet werden, um einen anzeigen Amen für das Zertifikat anzugeben.|  
|`<clear>`|Löscht alle Zertifikate aus der Sammlung vertrauenswürdiger Aussteller.|  
|`<remove thumbprint=xs:string>`|Entfernt ein Zertifikat aus der Sammlung vertrauenswürdiger Aussteller. Das Zertifikat wird mit dem- `thumbprint` Attribut angegeben. Dieses Attribut ist erforderlich.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Konfiguriert die Aussteller Namen Registrierung. **Wichtig:**  Das- `type` Attribut des- `<issuerNameRegistry>` Elements muss auf die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse verweisen, damit das- `<trustedIssuers>` Element gültig ist.|  
  
## <a name="remarks"></a>Bemerkungen  
 Windows Identity Foundation (WIF) bietet eine einzige Implementierung der- <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse, die standardmäßig die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse implementiert. Die Registrierung des Konfigurations Aussteller namens verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen werden. In der Liste werden die einzelnen Aussteller Namen mit dem X. 509-Zertifikat verknüpft, das zum Überprüfen der Signatur der vom Aussteller erzeugten Token erforderlich ist. Die Liste der vertrauenswürdigen Aussteller Zertifikate wird unter dem- `<trustedIssuers>` Element angegeben. Jedes Element in der Liste ordnet einen mmamonischen Aussteller Namen dem X. 509-Zertifikat zu, das zum Überprüfen der Signatur von Token benötigt wird, die von diesem Aussteller erstellt werden. Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und mithilfe des- `<add>` Elements hinzugefügt. Sie können Aussteller (Zertifikate) aus der Liste löschen oder entfernen, indem Sie `<clear>` die `<remove>` Elemente und verwenden.  
  
 Das- `type` Attribut des- `<issuerNameRegistry>` Elements muss auf die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse verweisen, damit das- `<trustedIssuers>` Element gültig ist.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
