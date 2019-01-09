---
title: '&lt;add&gt; von &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 5a61aefd92390eefb95d1f3e39236e53fa264990
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151501"
---
# <a name="ltaddgt-of-ltentriesgt"></a>&lt;add&gt; von &lt;entries&gt;
Stellt einen Routingeintrag dar, der einem Clientendpunkt, der zuvor definiert wurde, einen Filter zuordnet. Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.  
  
 \<system.serviceModel>  
\<Routing >  
\<FilterTables >  
\<FilterTable >  
\<Einträge >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|backupList|Eine Zeichenfolge, die einen Verweis auf eine Sicherungsliste von Endpunkten angibt.|  
|Endpunkt (endpoint)|Eine Zeichenfolge, die einen Verweis auf einen Clientendpunkt angibt, der Meldungen empfängt, die dem mit dem `filterName`-Attribut angegebenen Filter entsprechen.|  
|filterName|Eine Zeichenfolge, die einen Verweis auf ein Filterelement angibt.|  
|priority|Eine ganze Zahl, die die Priorität dieses Eintrags angibt.<br /><br /> Die Einträge in der Routingtabelle werden auf Grundlage der Priorität ausgewertet, wobei 0 für die niedrigste Priorität steht. Alle Einträge für eine bestimmte Priorität werden gleichzeitig ausgewertet; wenn kein übereinstimmender Eintrag für die aktuelle Priorität gefunden wird, wird die nächste Prioritätsstufe ausgewertet.<br /><br /> Dieser Wert ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Ein Konfigurationsabschnitt, der Routingzuordnungseinträge enthält.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
