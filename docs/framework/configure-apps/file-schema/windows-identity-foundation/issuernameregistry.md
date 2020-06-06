---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251964"
---
# \<issuerNameRegistry>
Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|type|Ein Typ, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerNameRegistry> . Weitere Informationen zum Angeben eines benutzerdefinierten finden Sie `type` unter [Custom Type References].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|Wenn das- `type` Attribut die konfigurationsbasierte Aussteller Namen Registrierung (die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse) angibt, [\<trustedIssuers>](trustedissuers.md) muss das-Element angegeben werden. Das- [\<trustedIssuers>](trustedissuers.md) Element kann- `<add>` ,-oder- `<clear>` `<remove>` Elemente als untergeordnete Elemente annehmen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Alle Aussteller Token werden mithilfe der Aussteller Namen Registrierung überprüft. Dies ist ein Objekt, das von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerNameRegistry> . Die Aussteller Namen Registrierung wird verwendet, um einem kryptografiematerial, das zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller erstellt werden, einen mnetmonischen Namen zuzuordnen. Die Aussteller Namen Registrierung verwaltet eine Liste der Aussteller, die von der Anwendung der vertrauenden Seite als vertrauenswürdig eingestuft werden. Der Typ der Aussteller Namen Registrierung wird mithilfe des- `type` Attributs angegeben. Das- `<issuerNameRegistry>` Element kann ein oder mehrere untergeordnete-Elemente aufweisen, die die Konfiguration für den angegebenen Typ bereitstellen. Die Logik, die diese untergeordneten Elemente verarbeitet, wird durch Überschreiben der-Methode bereitgestellt <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> .  
  
 WIF bietet standardmäßig einen Registrierungs Typ für einen einzelnen Aussteller Namen, die- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse. Diese Klasse verwendet einen Satz vertrauenswürdiger Aussteller Zertifikate, die in der Konfiguration angegeben sind. Hierfür ist ein untergeordnetes Konfigurationselement erforderlich, `<trustedIssuers>` unter dem die Sammlung vertrauenswürdiger Aussteller Zertifikate konfiguriert ist. Vertrauenswürdige Zertifikate werden mithilfe der ASN. 1-codierten Form des Zertifikat Fingerabdrucks angegeben und der Auflistung mithilfe der `<add>` Elemente, oder hinzugefügt bzw. daraus entfernt `<clear>` `<remove>` .  
  
 Das- `<issuerNameRegistry>` Element wird durch die- <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse dargestellt.  
  
> [!NOTE]
> Die Angabe des- `<issuerNameRegistry>` Elements als untergeordnetes Element des-Elements wurde als [\<identityConfiguration>](identityconfiguration.md) veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie die konfigurationsbasierte Aussteller Namen Registrierung angegeben wird.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
