---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942668"
---
# <a name="issuernameregistry"></a>\<issuerNameRegistry>
Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Ein Typ, der von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird. Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|Wenn das `type` -Attribut die konfigurationsbasierte Aussteller Namen Registrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse) angibt, müssen die [ \<Treuhänder >](trustedissuers.md) -Element angegeben werden. `<clear>`Das `<remove>` `<add>` [ \<Element "Treuhänder >](trustedissuers.md) " kann-,-oder-Elemente als untergeordnete Elemente annehmen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Alle Aussteller Token werden mithilfe der Aussteller Namen Registrierung überprüft. Dies ist ein Objekt, das von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> -Klasse abgeleitet wird. Die Aussteller Namen Registrierung wird verwendet, um einem kryptografiematerial, das zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller erstellt werden, einen mnetmonischen Namen zuzuordnen. Die Aussteller Namen Registrierung verwaltet eine Liste der Aussteller, die von der Anwendung der vertrauenden Seite als vertrauenswürdig eingestuft werden. Der Typ der Aussteller Namen Registrierung wird mithilfe des `type` -Attributs angegeben. Das `<issuerNameRegistry>` -Element kann ein oder mehrere untergeordnete-Elemente aufweisen, die die Konfiguration für den angegebenen Typ bereitstellen. Die Logik, die diese untergeordneten Elemente verarbeitet, wird durch <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Überschreiben der-Methode bereitgestellt.  
  
 WIF bietet standardmäßig einen Registrierungs Typ für einen einzelnen Aussteller Namen, die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse. Diese Klasse verwendet einen Satz vertrauenswürdiger Aussteller Zertifikate, die in der Konfiguration angegeben sind. Hierfür ist ein untergeordnetes Konfigurationselement `<trustedIssuers>`erforderlich, unter dem die Sammlung vertrauenswürdiger Aussteller Zertifikate konfiguriert ist. Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und der Auflistung mithilfe `<add>`der Elemente, `<clear>`oder `<remove>` hinzugefügt bzw. daraus entfernt.  
  
 Das `<issuerNameRegistry>` -Element wird durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> -Klasse dargestellt.  
  
> [!NOTE]
> Die Angabe `<issuerNameRegistry>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
