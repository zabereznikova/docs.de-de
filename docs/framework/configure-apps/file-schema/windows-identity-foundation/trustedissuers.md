---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: 50fc7194823fb0c5c426fb54ffd50b17c3714ed9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251762"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Konfiguriert die Liste der vertrauenswürdigen Aussteller Zertifikate, die von der Konfigurations basierten Aussteller Namen Registrierung verwendet<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>werden ().  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerNameRegistry->** ](issuernameregistry.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Treuhänder >**  
  
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
 None  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Fügt der Auflistung vertrauenswürdiger Aussteller ein Zertifikat hinzu. Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben. Dieses Attribut ist erforderlich und sollte die ASN. 1-codierte Form des Zertifikat Fingerabdrucks enthalten. Das `name` -Attribut ist optional und kann verwendet werden, um einen anzeigen Amen für das Zertifikat anzugeben.|  
|`<clear>`|Löscht alle Zertifikate aus der Sammlung vertrauenswürdiger Aussteller.|  
|`<remove thumbprint=xs:string>`|Entfernt ein Zertifikat aus der Sammlung vertrauenswürdiger Aussteller. Das Zertifikat wird mit dem `thumbprint` -Attribut angegeben. Dieses Attribut ist erforderlich.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Konfiguriert die Aussteller Namen Registrierung. **Wichtig:**  Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.|  
  
## <a name="remarks"></a>Hinweise  
 Windows Identity Foundation (WIF) bietet eine einzige Implementierung <xref:System.IdentityModel.Tokens.IssuerNameRegistry> der-Klasse, die standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse implementiert. Die Registrierung des Konfigurations Aussteller namens verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen werden. In der Liste werden die einzelnen Aussteller Namen mit dem X. 509-Zertifikat verknüpft, das zum Überprüfen der Signatur der vom Aussteller erzeugten Token erforderlich ist. Die Liste der vertrauenswürdigen Aussteller Zertifikate wird unter dem `<trustedIssuers>` -Element angegeben. Jedes Element in der Liste ordnet einen mmamonischen Aussteller Namen dem X. 509-Zertifikat zu, das zum Überprüfen der Signatur von Token benötigt wird, die von diesem Aussteller erstellt werden. Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und mithilfe `<add>` des-Elements hinzugefügt. Sie können Aussteller (Zertifikate) aus der Liste löschen oder entfernen, indem Sie `<clear>` die `<remove>` Elemente und verwenden.  
  
 Das `type` -Attribut `<issuerNameRegistry>` des-Elements muss auf <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> die-Klasse `<trustedIssuers>` verweisen, damit das-Element gültig ist.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
