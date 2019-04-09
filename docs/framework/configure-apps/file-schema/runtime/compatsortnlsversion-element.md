---
title: <CompatSortNLSVersion> Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfd241056947fbf1daf48b84ff41e3f74ff7b8de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195773"
---
# <a name="compatsortnlsversion-element"></a>\<CompatSortNLSVersion >-Element
Gibt an, dass die Laufzeit Sortierreihenfolgen von Legacyversionen beim Vergleichen von Zeichenfolgen verwenden soll.  
  
 \<configuration>  
\<runtime>  
\<CompatSortNLSVersion >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt die Gebietsschema-ID an, deren Sortierreihenfolge verwendet werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|4096|Die Gebietsschema-ID, die eine andere Sortierreihenfolge darstellt. In diesem Fall stellt 4096 die Sortierreihenfolge von [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] und früheren Versionen dar.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Da von Zeichenfolge vergleichen, Sortieren und Schreibweise Vorgänge ausgeführt der <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> -Klasse in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] entsprechen dem Unicode 5.1-standard, die Ergebnisse der Methoden zum Zeichenfolgenvergleich wie z. B. <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> und <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> weicht möglicherweise von frühere Versionen von .NET Framework. Wenn Ihre Anwendung von Legacyverhalten abhängig ist, können Sie die Regeln für den Vergleich und die Sortierung von Zeichenfolgen aus [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] und früheren Versionen wiederherstellen, indem Sie das `<CompatSortNLSVersion>`-Element in der Konfigurationsdatei der Anwendung angeben.  
  
> [!IMPORTANT]
>  Zum Wiederherstellen von Zeichenfolgenvergleichs- und Zeichenfolgensortierregeln von Legacyversionen muss auch die sort00001000.dll-Dynamic Link Library auf dem lokalen System verfügbar sein.  
  
 Sie können Zeichenfolgensortier- und Zeichenfolgenvergleichsregeln von Legacyversionen auch in einer bestimmten Anwendungsdomäne verwenden, indem Sie die Zeichenfolge "NetFx40_Legacy20SortingBehavior" an die <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>-Methode beim Erstellen der Anwendungsdomäne übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.String>-Objekte instanziiert und die <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>-Methode aufgerufen, um sie mithilfe der Konventionen der aktuellen Kultur zu vergleichen.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Wenn Sie das Beispiel unter [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ausführen, wird die folgende Ausgabe angezeigt.  
  
```  
sta follows a in the sort order.  
```  
  
 Diese unterscheidet sich vollkommen von der Ausgabe, die bei Ausführung des Beispiels unter [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] angezeigt wird.  
  
```  
sta equals a in the sort order.  
```  
  
 Wenn Sie jedoch dem Verzeichnis des Beispiels die folgende Konfigurationsdatei hinzufügen und dann das Beispiel unter [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ausführen, ist die Ausgabe identisch mit der bei einer Ausführung unter [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
