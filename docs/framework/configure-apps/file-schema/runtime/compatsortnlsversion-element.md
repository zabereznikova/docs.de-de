---
title: <CompatSortNLSVersion>-Element
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
ms.openlocfilehash: b426eaaa2dab4d54ea4c82483c079428f3bfac57
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689913"
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
|4096|Die Gebietsschema-ID, die eine andere Sortierreihenfolge darstellt. In diesem Fall stellt 4096 die Sortierreihenfolge der .NET Framework 3.5 und früheren Versionen dar.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Da Zeichenfolge vergleichen, Sortieren und Schreibweise Vorgänge, durch ausgeführt die <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> Klasse in .NET Framework 4 entsprechen dem Unicode 5.1-standard, die Ergebnisse der Methoden zum Zeichenfolgenvergleich wie z. B. <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> und <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> weicht möglicherweise von frühere Versionen von .NET Framework. Wenn Ihre Anwendung von Legacyverhalten abhängig ist, können Sie wiederherstellen, der Zeichenfolgenvergleich und-Sortierung Regeln, die in der .NET Framework 3.5 und früheren Versionen verwendet werden, durch Einschließen der `<CompatSortNLSVersion>` Element in der Konfigurationsdatei Ihrer Anwendung.  
  
> [!IMPORTANT]
>  Zum Wiederherstellen von Zeichenfolgenvergleichs- und Zeichenfolgensortierregeln von Legacyversionen muss auch die sort00001000.dll-Dynamic Link Library auf dem lokalen System verfügbar sein.  
  
 Sie können Zeichenfolgensortier- und Zeichenfolgenvergleichsregeln von Legacyversionen auch in einer bestimmten Anwendungsdomäne verwenden, indem Sie die Zeichenfolge "NetFx40_Legacy20SortingBehavior" an die <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>-Methode beim Erstellen der Anwendungsdomäne übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.String>-Objekte instanziiert und die <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>-Methode aufgerufen, um sie mithilfe der Konventionen der aktuellen Kultur zu vergleichen.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Wenn Sie das Beispiel für die .NET Framework 4 ausführen, wird die folgende Ausgabe angezeigt.  
  
```  
sta follows a in the sort order.  
```  
  
 Dies unterscheidet sich vollständig von der Ausgabe, die angezeigt wird, wenn Sie das Beispiel für .NET Framework 3.5 ausführen.  
  
```  
sta equals a in the sort order.  
```  
  
 Wenn Sie die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann auf die .NET Framework 4 das Beispiel ausführen, ist jedoch die Ausgabe identisch, die durch das Beispiel erstellt wird, wenn es auf .NET Framework 3.5 ausgeführt wird.  
  
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
