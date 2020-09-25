---
title: <UseRandomizedStringHashAlgorithm>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: 148d55c8b8a63737867c4bfdf3ab118dfdefd6f9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174094"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm>-Element

Bestimmt, ob die Common Language Runtime Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Hashcodes für Zeichenfolgen pro Anwendungsdomäne berechnet werden.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`0`|Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen nicht pro Anwendungsdomäne; es wird ein einzelner Algorithmus verwendet, um Hashcodes für Zeichenfolgen zu berechnen. Dies ist die Standardeinstellung.|  
|`1`|Die Common Language Runtime berechnet Hashcodes für Zeichenfolgen pro Anwendungsdomäne. Identische Zeichenfolgen in unterschiedlichen Anwendungsdomänen und in verschiedenen Prozessen weisen unterschiedliche Hashcodes auf.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Standardmäßig verwenden die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode einen einzelnen Hashalgorithmus, der einen über verschiedene Anwendungsdomänen hinweg konsistenten Hashcode erzeugt. Dies entspricht dem Festlegen des `enabled`-Attributs des `<UseRandomizedStringHashAlgorithm>`-Elements auf `0`. Dies ist der Hash Algorithmus, der in der .NET Framework 4 verwendet wird.  
  
 Die <xref:System.StringComparer>-Klasse und die <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>-Methode können auch einen anderen Hashalgorithmus verwenden, der Hashcodes pro Anwendungsdomäne berechnet. Dadurch variieren Hashcodes für identische Zeichenfolgen von Anwendungsdomäne zu Anwendungsdomäne. Dies ist eine Opt-In-Funktion; um sie zu nutzen, müssen Sie das `enabled`-Attribut des `<UseRandomizedStringHashAlgorithm>`-Elements auf `1` festlegen.  
  
 Die Zeichenfolgensuche in einer Hashtabelle ist in der Regel eine O(1)-Operation. Wenn jedoch eine große Anzahl von Kollisionen auftritt, kann die Suche ein O (n<sup>2</sup>)-Vorgang werden. Sie können das `<UseRandomizedStringHashAlgorithm>`-Konfigurationselement verwenden, um einen zufälligen Hashalgorithmus pro Anwendungsdomäne zu generieren. Dadurch wird die Anzahl der potenziellen Konflikte beschränkt, insbesondere wenn die Schlüssel, aus denen die Hashcodes berechnet werden, auf Dateneingaben durch Benutzer basieren.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine `DisplayString`-Klasse definiert, die die private Zeichenfolgenkonstante `s` enthält, deren Wert "Dies ist eine Zeichenfolge" lautet. Außerdem enthält sie eine `ShowStringHashCode`-Methode, die den Zeichenfolgenwert und dessen Hashcode zusammen mit dem Namen der Anwendungsdomäne anzeigt, in der die Methode ausgeführt wird.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Wenn Sie das Beispiel ausführen, ohne eine Konfigurationsdatei anzugeben, wird die folgende Ausgabe angezeigt. Beachten Sie, dass die Hashcodes für die Zeichenfolge in den zwei Anwendungsdomänen identisch sind.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Wenn Sie jedoch die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel ausführen, unterscheiden sich die Hashcodes je nach Anwendungsdomäne.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Wenn die Konfigurationsdatei vorhanden ist, zeigt das Beispiel die folgende Ausgabe an:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
