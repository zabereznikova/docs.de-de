---
title: <performanceCounters>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697154"
---
# <a name="performancecounters-element"></a>\<performanceCounters >-Element

Gibt die Größe des globalen Speichers an, der von den Leistungsindikatoren freigegeben wird.

[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. Diagnostics >** ](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<Performance Counters >**  

## <a name="syntax"></a>Syntax

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|FileMappingSize|Erforderliches Attribut.<br /><br /> Gibt die Größe des globalen Speichers in Bytes an, der von den Leistungsindikatoren gemeinsam genutzt wird. Der Standard ist 524288.|

### <a name="child-elements"></a>Untergeordnete Elemente

None.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`Configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`system.diagnostics`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|

## <a name="remarks"></a>Hinweise

Leistungsindikatoren verwenden eine Speicher Abbild Datei oder freigegebenen Arbeitsspeicher, um Leistungsdaten zu veröffentlichen.  Die Größe des freigegebenen Speichers bestimmt, wie viele Instanzen gleichzeitig verwendet werden können.  Es gibt zwei Arten von gemeinsam genutzten Arbeitsspeicher: globaler gemeinsam genutzter Speicher und separater frei gegebener Speicher.  Der globale freigegebene Speicher wird von allen Leistungs Indikatorenkategorien verwendet, die mit den .NET Framework Version 1,0 oder 1,1 installiert werden.  Die mit der .NET Framework Version 2,0 installierten Leistungs Indikatorenkategorien verwenden separaten freigegebenen Arbeitsspeicher, wobei jede Leistungs Indikatorenkategorie über einen eigenen Arbeitsspeicher verfügt.

Die Größe des globalen freigegebenen Speichers kann nur mit einer Konfigurationsdatei festgelegt werden.  Die Standardgröße beträgt 524.288 Byte, die maximale Größe beträgt 33.554.432 bytes, und die Mindestgröße beträgt 32.768 Bytes.  Da der globale freigegebene Speicher von allen Prozessen und Kategorien gemeinsam genutzt wird, gibt der erste Ersteller die Größe an.  Wenn Sie die Größe in der Anwendungs Konfigurationsdatei definieren, wird diese Größe nur verwendet, wenn die Anwendung die erste Anwendung ist, die die Ausführung der Leistungsindikatoren bewirkt.  Daher ist der richtige Speicherort zum Angeben des `filemappingsize` Werts die Datei Machine. config.  Der Arbeitsspeicher im globalen gemeinsam genutzten Arbeitsspeicher kann nicht von einzelnen Leistungsindikatoren freigegeben werden. Folglich ist der globale freigegebene Speicher erschöpft, wenn eine große Anzahl von Leistungsindikator Instanzen mit unterschiedlichen Namen erstellt wird.

Bei der Größe des separaten freigegebenen Speichers wird zuerst auf den DWORD-dateimappingsize-Wert im Registrierungsschlüssel HKEY_LOCAL_MACHINE \system\currentcontrolset\services\\ *\<Kategoriename >* \Performance verwiesen, gefolgt von dem Wert, der für den globalen gemeinsam genutzten Speicher in der Konfigurationsdatei angegeben wurde. Wenn der FileMappingSize-Wert nicht vorhanden ist, wird die separate Größe des freigegebenen Speichers auf ein viertes (1/4) die globale Einstellung in der Konfigurationsdatei festgelegt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
