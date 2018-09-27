---
title: '&lt;"issuerNameRegistry"&gt;'
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: de3ceb5d84d17307c69e9155834a0a584e6920a1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399153"
---
# <a name="ltissuernameregistrygt"></a>&lt;"issuerNameRegistry"&gt;
Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
\<"issuerNameRegistry" >  
  
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
|Typ|Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse. Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Wenn die `type` Attribut gibt an, der konfigurationsbasierten ausstellernamenregistrierung (die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse), wird die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element muss angegeben werden. Die [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element dauert `<add>`, `<clear>`, oder `<remove>` -Elemente als untergeordnete Elemente.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Alle ausstellertoken werden überprüft, eine Ausstellernamen-Registrierung verwenden. Dies ist ein Objekt, das von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse. Die Ausstellernamen-Registrierung wird verwendet, um einen merknamen kryptografischen Informationen zuzuordnen, die benötigt werden, um zu überprüfen, ob die Signaturen von Token, die vom entsprechenden Aussteller erzeugt werden. Die Ausstellernamen-Registrierung verwaltet eine Liste der Zertifikataussteller, die die Anwendung der vertrauenden Seite (Relying Party, RP) vertraut. Der Typ, der die Ausstellernamen-Registrierung angegeben ist, mit der `type` Attribut. Die `<issuerNameRegistry>` -Element kann eine oder mehrere untergeordnete Elemente, die Konfiguration für den angegebenen Typ aufweisen. Geben Sie die Logik, die verarbeitet diese untergeordneten Elemente durch Überschreiben der <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Methode.  
  
 WIF stellt einen einzelnen Aussteller namens Registrierungstyp standardmäßig die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse. Diese Klasse verwendet eine Reihe von Zertifikaten vertrauenswürdiger Aussteller, die in der Konfiguration angegeben werden. Es muss ein untergeordnetes Konfigurationselement `<trustedIssuers>`, unter dem die Auflistung von Zertifikaten vertrauenswürdiger Aussteller konfiguriert ist. Vertrauenswürdige Zertifikate angegeben sind, mit der ASN. 1-codierte Form des Zertifikatfingerabdrucks und hinzugefügt oder aus der Auflistung entfernt werden, mithilfe von `<add>`, `<clear>`, oder `<remove>` Elemente.  
  
 Die `<issuerNameRegistry>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse.  
  
> [!NOTE]
>  Angeben der `<issuerNameRegistry>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt. Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie an den Aussteller für die Konfiguration basiert-Registrierung.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
