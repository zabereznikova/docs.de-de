---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b506b8ef14246ee954adb0a16102f4bb208106b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltpersistenceprovidergt"></a>&lt;persistenceProvider&gt;
Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<ServiceBehaviors >  
\<Verhalten >  
\<PersistenceProvider >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|persistenceOperationTimeout|Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird. Die Standardeinstellung ist "00: 00:30".|  
|Typ|Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren. Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
