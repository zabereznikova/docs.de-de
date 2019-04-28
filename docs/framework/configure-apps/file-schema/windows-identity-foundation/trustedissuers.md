---
title: <trustedIssuers>
ms.date: 03/30/2017
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
author: BrucePerlerMS
ms.openlocfilehash: cebfc2f3598f32f233db6039dfe82076d2ffce46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790480"
---
# <a name="trustedissuers"></a>\<trustedIssuers>
Konfiguriert die Liste der vertrauenswürdigen ausstellerzertifikate, die von der konfigurationsbasierten ausstellernamenregistrierung verwendet (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration>  
\<issuerNameRegistry>  
\<trustedIssuers>  
  
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
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<add thumbprint=xs:string name=xs:string>`|Fügt ein Zertifikat zur Auflistung der vertrauenswürdigen Aussteller an. Das Zertifikat ist angegeben, mit der `thumbprint` Attribut. Dieses Attribut ist erforderlich und sollte das Formular codierte ASN. 1 den Fingerabdruck des Zertifikats enthalten. Die `name` Attribut ist optional und kann verwendet werden, um einen Anzeigenamen für das Zertifikat anzugeben.|  
|`<clear>`|Löscht alle Zertifikate aus der Auflistung der vertrauenswürdigen Aussteller an.|  
|`<remove thumbprint=xs:string>`|Entfernt ein Zertifikat aus der Auflistung der vertrauenswürdigen Aussteller an. Das Zertifikat ist angegeben, mit der `thumbprint` Attribut. Dieses Attribut ist erforderlich.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Konfiguriert die Ausstellernamen-Registrierung. **Wichtig:**  Die `type` Attribut der `<issuerNameRegistry>` Elementverweis muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse für die `<trustedIssuers>` Element gültig ist.|  
  
## <a name="remarks"></a>Hinweise  
 Windows Identity Foundation (WIF) bietet eine einzige Implementierung der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse standardmäßig den <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse. Die Konfiguration Ausstellernamen-Registrierung verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen wird. Die Liste ordnet jeden Ausstellernamen dem x. 509-Zertifikat, das benötigt wird, um zu überprüfen, ob die Signatur von Token, die vom Aussteller erzeugt werden. Die Liste von Zertifikaten vertrauenswürdiger Aussteller wird angegeben, unter dem `<trustedIssuers>` Element. Jedes Element in der Liste ordnet einen Ausstellernamen für die mnemonischen, mit dem x. 509-Zertifikat, das zum Überprüfen der Signatur von Token, die von diesem Aussteller erzeugt erforderlich ist. Vertrauenswürdige Zertifikate mithilfe der ASN. 1-codierte Form der Fingerabdruck des Zertifikats angegeben werden und werden die Auflistung hinzugefügt, mit `<add>` Element. Sie können das Löschen oder Entfernen von Aussteller (Zertifikate) aus der Liste mit den `<clear>` und `<remove>` Elemente.  
  
 Die `type` Attribut der `<issuerNameRegistry>` Elementverweis muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse für die `<trustedIssuers>` Element gültig ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie an den Aussteller für die Konfiguration basiert-Registrierung.  
  
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
