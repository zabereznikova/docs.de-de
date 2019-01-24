---
title: '&lt;add&gt; von &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 1d3b61fa6653b3910e65b95fa96fd0657e72bf7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632907"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a>&lt;add&gt; von &lt;namespaceTable&gt;
Stellt ein Konfigurationselement dar, das eine Namespace-/Präfix-Zuordnung enthält, die zu Routingzwecken in XPath-Filtern verwendet werden kann.  
  
 \<system.serviceModel>  
\<routing>  
\<namespaceTable>  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|namespace|Eine Zeichenfolge, die den Namespace enthält.|  
|prefix|Eine Zeichenfolge, die das Präfix für diesen Namespace enthält.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namespaceTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.|  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
