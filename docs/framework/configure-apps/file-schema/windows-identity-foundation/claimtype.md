---
title: '&lt;"ClaimType"&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47234958"
---
# <a name="ltclaimtypegt"></a>&lt;"ClaimType"&gt;
Gibt einen einzelnen erforderliche oder optionale Anspruch eingehender Sicherheitstoken an.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<ClaimTypeRequired >  
\<"ClaimType" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Der Anspruchstyp. In der Regel ein URI. Erforderlich.|  
|Optional|Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist. Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClaimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.|
