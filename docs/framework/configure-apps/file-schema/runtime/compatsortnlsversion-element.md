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
ms.openlocfilehash: 30afeb2ab9380db75cbeb723ea15a23e4313c9e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154269"
---
# <a name="compatsortnlsversion-element"></a>\<CompatSortNLSVersion> Element
Gibt an, dass die Laufzeit Sortierreihenfolgen von Legacyversionen beim Vergleichen von Zeichenfolgen verwenden soll.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<CompatSortNLSVersion
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt die Gebietsschema-ID an, deren Sortierreihenfolge verwendet werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|4096|Die Gebietsschema-ID, die eine andere Sortierreihenfolge darstellt. In diesem Fall stellt 4096 die Sortierreihenfolge von .NET Framework 3.5 und früheren Versionen dar.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Da Zeichenfolgenvergleichs-, Sortier- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> und Großformatialoperationen, die von der Klasse in .NET Framework 4 <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> ausgeführt werden, dem Unicode 5.1-Standard entsprechen, können die Ergebnisse von Zeichenfolgenvergleichsmethoden, wie z. B. und können von früheren Versionen von .NET Framework abweichen. Wenn Ihre Anwendung vom Älterenverhalten abhängt, können Sie die Zeichenfolgenvergleichs- und Sortierregeln `<CompatSortNLSVersion>` wiederherstellen, die in der .NET Framework 3.5- und früheren Version verwendet wurden, indem Sie das Element in die Konfigurationsdatei Ihrer Anwendung einbeziehen.  
  
> [!IMPORTANT]
> Zum Wiederherstellen von Zeichenfolgenvergleichs- und Zeichenfolgensortierregeln von Legacyversionen muss auch die sort00001000.dll-Dynamic Link Library auf dem lokalen System verfügbar sein.  
  
 Sie können Zeichenfolgensortier- und Zeichenfolgenvergleichsregeln von Legacyversionen auch in einer bestimmten Anwendungsdomäne verwenden, indem Sie die Zeichenfolge "NetFx40_Legacy20SortingBehavior" an die <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>-Methode beim Erstellen der Anwendungsdomäne übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.String>-Objekte instanziiert und die <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>-Methode aufgerufen, um sie mithilfe der Konventionen der aktuellen Kultur zu vergleichen.  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 Wenn Sie das Beispiel auf .NET Framework 4 ausführen, wird die folgende Ausgabe angezeigt:
  
```console
sta follows a in the sort order.  
```  
  
 Dies unterscheidet sich völlig von der Ausgabe, die angezeigt wird, wenn Sie das Beispiel auf .NET Framework 3.5 ausführen:
  
```console
sta equals a in the sort order.  
```  
  
 Wenn Sie jedoch die folgende Konfigurationsdatei zum Verzeichnis des Beispiels hinzufügen und dann das Beispiel auf .NET Framework 4 ausführen, ist die Ausgabe mit der Ausgabe identisch, die vom Beispiel erstellt wird, wenn sie auf .NET Framework 3.5 ausgeführt wird.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
