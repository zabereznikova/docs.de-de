---
title: '&lt;trustedIssuers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 26f3d4f0b272168083bed2bbe249532181a6db67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lttrustedissuersgt"></a>&lt;trustedIssuers&gt;
Konfiguriert die Liste von Zertifikaten vertrauenswürdiger Aussteller, die von der konfigurationsbasierte ausstellernamenregistration verwendet (<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>).  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
\<IssuerNameRegistry >  
\<TrustedIssuers >  
  
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
|`<add thumbprint=xs:string name=xs:string>`|Fügt ein Zertifikat auf die Auflistung vertrauenswürdiger Aussteller. Das Zertifikat wird angegeben, mit der `thumbprint` Attribut. Dieses Attribut ist erforderlich und sollte das Formular codierte ASN. 1 den Fingerabdruck des Zertifikats enthalten. Die `name` Attribut ist optional und kann verwendet werden, um einen Anzeigenamen für das Zertifikat anzugeben.|  
|`<clear>`|Löscht alle Zertifikate aus der Auflistung vertrauenswürdiger Aussteller.|  
|`<remove thumbprint=xs:string>`|Entfernt ein Zertifikat aus der Auflistung vertrauenswürdiger Aussteller. Das Zertifikat wird angegeben, mit der `thumbprint` Attribut. Dieses Attribut ist erforderlich.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IssuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Konfiguriert die ausstellernamenregistration an. **Wichtig:** der `type` Attribut des der `<issuerNameRegistry>` Elementverweis muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse für die `<trustedIssuers>` Element gültig ist.|  
  
## <a name="remarks"></a>Hinweise  
 Windows Identity Foundation (WIF) bietet eine einzelne Implementierung von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse ausgegeben, die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse. Die Konfiguration ausstellernamenregistration verwaltet eine Liste der vertrauenswürdigen Aussteller, die aus der Konfiguration geladen wird. Jeder Ausstellername verknüpft mit dem x. 509-Zertifikat, das erforderlich ist, zum Überprüfen der Signatur von Token, die von den Aussteller erzeugten. Die Liste von Zertifikaten vertrauenswürdiger Aussteller wird angegeben, unter der `<trustedIssuers>` Element. Jedes Element in der Liste ordnet das x. 509-Zertifikat, das zum Überprüfen der Signatur des Tokens, die von diesem Aussteller erzeugten erforderlich ist eine mnemonische Ausstellernamen. Vertrauenswürdiger Zertifikate mithilfe der ASN. 1-codierte Form der Fingerabdruck des Zertifikats angegeben werden und werden mithilfe die Auflistung hinzugefügt `<add>` Element. Sie können löschen oder Entfernen von Aussteller (Zertifikate) aus der Liste mit den `<clear>` und `<remove>` Elemente.  
  
 Die `type` Attribut des der `<issuerNameRegistry>` Elementverweis muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> -Klasse für die `<trustedIssuers>` Element gültig ist.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie an der Konfiguration auf der Basis-Aussteller Namen Registrierung.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
