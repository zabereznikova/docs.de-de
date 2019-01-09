---
title: '&lt;diagnostics&gt; für die Aktivierung'
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 28f051a7ab06dbc1b40f804c56071818eb37e88b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144976"
---
# <a name="ltdiagnosticsgt-for-activation"></a>&lt;diagnostics&gt; für die Aktivierung
Konfiguriert die Diagnosefunktionen von Windows Communication Foundation (WCF)-Listener.  
  
 \<system.serviceModel.activation>  
\<Diagnose >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>Typ  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`performanceCountersEnabled`|Ein boolescher Wert auf, der angibt, ob Leistungsindikatoren zu Diagnosezwecken aktiviert sind.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Enthält Konfigurationseinstellungen für den Listenerprozess SMSvcHost.exe.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
