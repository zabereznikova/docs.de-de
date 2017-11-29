---
title: '&lt;add&gt; von &lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 964e1ebc3dfc39a06b82dd1b6438e34642635393
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a>&lt;add&gt; von &lt;allowAccounts&gt;
Gibt ein Benutzerkonto für Prozesse an, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.  
  
 \<system.serviceModel.activation >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|securityIdentifier|Eine Zeichenfolge, die einen eindeutigen Bezeichner angibt, der verwendet wird, um ein Benutzerkonto zu identifizieren. Die Standardwerte sind LocalSystem, Administrators, NS, LS und IIS_USRS.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AllowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Eine Auflistung von Konfigurationselementen, die ein `securityIdentifier`-Attribut zum Angeben von Benutzerkonten für Prozesse enthalten, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Konfigurationsbeispiel werden die fünf Standardbezeichner dieser Auflistung für Benutzerkonten hinzugefügt.  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
