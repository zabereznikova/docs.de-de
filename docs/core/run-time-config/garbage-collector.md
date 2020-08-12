---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915989"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a>Laufzeitkonfigurationsoptionen für die Garbage Collection

Diese Seite enthält Informationen zu Garbage-Collector-Einstellungen (GC), die zur Laufzeit geändert werden können. Verwenden Sie diese Einstellungen, wenn Sie versuchen, die maximale Leistung einer ausgeführten App zu erzielen. Die Standardwerte bieten jedoch in typischen Situationen eine optimale Leistung für die meisten Anwendungen.

Einstellungen werden auf dieser Seite in Gruppen angeordnet. Die Einstellungen in den einzelnen Gruppen werden häufig zusammen verwendet, um ein bestimmtes Ergebnis zu erzielen.

> [!NOTE]
>
> - Diese Einstellungen können auch dynamisch von der App geändert werden, während diese ausgeführt wird, sodass die von Ihnen festgelegten Laufzeiteinstellungen überschrieben werden können.
> - Einige Einstellungen, wie z. B. die [Latenzebene](../../standard/garbage-collection/latency.md), werden in der Regel nur über die API zur Entwurfszeit festgelegt. Diese Einstellungen werden auf dieser Seite weggelassen.
> - Verwenden Sie für Zahlenwerte für Einstellungen in der Datei *runtimeconfig.json* die Dezimalschreibweise und für Einstellungen in der Umgebungsvariablen die Hexadezimalnotation. Bei hexadezimalen Werten können Sie sie mit dem oder ohne das Präfix „0x“ angeben.

## <a name="flavors-of-garbage-collection"></a>Varianten der Garbage Collection

Die zwei Hauptvarianten der Garbage Collection sind Arbeitsstation-GC und Server-GC. Weitere Informationen zu den Unterschieden zwischen diesen beiden Varianten finden Sie unter [Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server](../../standard/garbage-collection/workstation-server-gc.md).

Die Untervarianten der Garbage Collection sind Hintergrund-GC und nicht gleichzeitige GC.

Verwenden Sie die folgenden Einstellungen, um Varianten der Garbage Collection auszuwählen:

- [Garbage Collection für Arbeitsstationen und Server im Vergleich](#workstation-vs-server)
- [Garbage Collection im Hintergrund](#background-gc)

### <a name="workstation-vs-server"></a>Arbeitsstationen und Server im Vergleich

- Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet
- Standard: Arbeitsstation-Garbage Collection. Dies entspricht der Einstellung des Werts auf `false`.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false` – Arbeitsstation<br/>`true` – Server | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `ServerGarbageCollection` | `false` – Arbeitsstation<br/>`true` – Server | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_gcServer` | `0` – Arbeitsstation<br/>`1` – Server | .NET Core 1.0 |
| **app.config für .NET Framework** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false` – Arbeitsstation<br/>`true` – Server |  |

#### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a>Garbage Collection im Hintergrund

- Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist
- Standard: Garbage Collection im Hintergrund verwenden. Dies entspricht der Einstellung des Werts auf `true`.
- Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `ConcurrentGarbageCollection` | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_gcConcurrent` | `1` – Hintergrund-GC<br/>`0` – nicht gleichzeitige GC | .NET Core 1.0 |
| **app.config für .NET Framework** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC |  |

#### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a>Verwalten des Ressourceneinsatzes

Verwenden Sie die folgenden Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten:

- [Zuordnen](#affinitize)
- [Maske zuordnen](#affinitize-mask)
- [Bereiche zuordnen](#affinitize-ranges)
- [CPU-Gruppen](#cpu-groups)
- [Heapanzahl](#heap-count)
- [Heapgrenzwert](#heap-limit)
- [Heapgrenzwert (Prozent)](#heap-limit-percent)
- [Hohe Speicherauslastung (Prozent)](#high-memory-percent)
- [Grenzwerte pro Objektheap](#per-object-heap-limits)
- [Grenzwerte pro Objektheap (Prozent)](#per-object-heap-limit-percents)
- [VM beibehalten](#retain-vm)

Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).

### <a name="heap-count"></a>Heapanzahl

- Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden
- Gilt nur für die Garbage Collection des Servers.
- Wenn die [GC-Prozessoraffinität](#affinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu. (Verwenden Sie die Einstellungen [AffinitizeMask](#affinitize-mask) oder [AffinitizeRanges](#affinitize-ranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)
- Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.
- Weitere Informationen finden Sie unter [Hinweise zu GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapCount` | *Dezimalwert* | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCHeapCount` | *Hexadezimalwert* | .NET Core 3.0 |
| **app.config für .NET Framework** | [GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | *Dezimalwert* | .NET Framework 4.6.2 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Für eine Einschränkung der Heapanzahl auf 16 wären die Werte beispielsweise 16 für die JSON-Datei und 0x10 oder 10 für die Umgebungsvariable.

### <a name="affinitize-mask"></a>Maske zuordnen

- Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen
- Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird diese Einstellung ignoriert.
- Gilt nur für die Garbage Collection des Servers.
- Der Wert ist eine Bitmaske, die die für den Prozess verfügbaren Prozessoren definiert. Beispielsweise ist ein Dezimalwert von 1023 (oder ein Hexadezimalwert von 0x3FF oder 3FF bei Verwendung der Umgebungsvariablen) in Binärschreibweise 0011 1111 1111. Dies gibt an, dass die ersten zehn Prozessoren verwendet werden sollen. Geben Sie einen Dezimalwert von 1047552 (oder einen Hexadezimalwert von 0xFFC00 oder FFC00) an, der einem Binärwert von 1111 1111 1100 0000 0000 entspricht, um die nächsten zehn Prozessoren anzugeben, d. h. die Prozessoren 10 bis 19.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapAffinitizeMask` | *Dezimalwert* | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCHeapAffinitizeMask` | *Hexadezimalwert* | .NET Core 3.0 |
| **app.config für .NET Framework** | [GCHeapAffinitizeMask](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | *Dezimalwert* | .NET Framework 4.6.2 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a>Bereiche zuordnen

- Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen
- Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#affinitize-mask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.
- Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.
- Wenn die [GC-Prozessoraffinität](#affinitize) deaktiviert ist, wird diese Einstellung ignoriert.
- Gilt nur für die Garbage Collection des Servers.
- Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.GCHeapAffinitizeRanges` | Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern<br/>Unix-Beispiel: „1-10,12,50-52,70“<br/>Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“ | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCHeapAffinitizeRanges` | Durch Kommas getrennte Liste mit Prozessornummern oder Bereichen von Prozessornummern<br/>Unix-Beispiel: „1-10,12,50-52,70“<br/>Windows-Beispiel: „0:1-10,0:12,1:50-52,1:70“ | .NET Core 3.0 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a>CPU-Gruppen

- Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet

  Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert. Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.

- Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.
- Standard: GC wird nicht über CPU-Gruppen hinweg erweitert. Dies entspricht der Einstellung des Werts auf `0`.
- Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.CpuGroup` | `0` – deaktiviert<br/>`1` – aktiviert | .NET 5.0 |
| **Umgebungsvariable** | `COMPlus_GCCpuGroup` | `0` – deaktiviert<br/>`1` – aktiviert | .NET Core 1.0 |
| **app.config für .NET Framework** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false` – deaktiviert<br/>`true` – aktiviert |  |

> [!NOTE]
> Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden. Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.

### <a name="affinitize"></a>Zuordnen

- Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen. Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann. Für jeden GC-Thread wird ein Heap erstellt.
- Gilt nur für die Garbage Collection des Servers.
- Standard: Garbage Collection-Threads werden Prozessoren zugeordnet. Dies entspricht der Einstellung des Werts auf `false`.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.NoAffinitize` | `false` – zuordnen<br/>`true` – nicht zuordnen | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCNoAffinitize` | `0` – zuordnen<br/>`1` – nicht zuordnen | .NET Core 3.0 |
| **app.config für .NET Framework** | [GCNoAffinitize](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | `false` – zuordnen<br/>`true` – nicht zuordnen | .NET Framework 4.6.2 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a>Heapgrenzwert

- Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an
- Diese Einstellung gilt nur für 64-Bit-Computer.
- Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.
- Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container. Der Standardwert wird in folgenden Fällen angewendet:

  - Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.
  - [System.GC.HeapHardLimitPercent](#heap-limit-percent) ist nicht festgelegt.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimit` | *Dezimalwert* | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCHeapHardLimit` | *Hexadezimalwert* | .NET Core 3.0 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.

### <a name="heap-limit-percent"></a>Heapgrenzwert (Prozent)

- Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.
- Wenn außerdem [System.GC.HeapHardLimit](#heap-limit) festgelegt ist, wird diese Einstellung ignoriert.
- Diese Einstellung gilt nur für 64-Bit-Computer.
- Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.
- Diese Einstellung wird ignoriert, wenn die [Grenzwerte pro Objektheap](#per-object-heap-limits) konfiguriert sind.
- Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container. Der Standardwert wird in folgenden Fällen angewendet:

  - Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.
  - [System.GC.HeapHardLimit](#heap-limit) ist nicht festgelegt.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPercent` | *Dezimalwert* | .NET Core 3.0 |
| **Umgebungsvariable** | `COMPlus_GCHeapHardLimitPercent` | *Hexadezimalwert* | .NET Core 3.0 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.

### <a name="per-object-heap-limits"></a>Grenzwerte pro Objektheap

Sie können die zulässige Heapnutzung bei der Garbage Collection pro Objektheap angeben. Die verschiedenen Arten von Heaps sind: große Objektheaps (Large Object Heap, LOH), kleine Objektheaps (Small Object Heap, SOH) und fixierte Objektheaps (Pinned Object Heap, POH).

- Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` oder `COMPLUS_GCHeapHardLimitPOH` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` angeben. Andernfalls kann die Laufzeit nicht initialisiert werden.
- Der Standardwert für `COMPLUS_GCHeapHardLimitPOH` ist 0. `COMPLUS_GCHeapHardLimitSOH` und `COMPLUS_GCHeapHardLimitLOH` verfügen über keine Standardwerte.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitSOH` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitSOH` | *Hexadezimalwert* | .NET 5.0 |

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitLOH` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitLOH` | *Hexadezimalwert* | .NET 5.0 |

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPOH` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitPOH` | *Hexadezimalwert* | .NET 5.0 |

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Wenn Sie beispielsweise eine feste Heapgrenze von 200 MiB festlegen, würden die Werte für die JSON-Datei 209715200 und für die Umgebungsvariable 0xc800000 oder C800000 betragen.

### <a name="per-object-heap-limit-percents"></a>Grenzwerte pro Objektheap (Prozent)

Sie können die zulässige Heapnutzung bei der Garbage Collection pro Objektheap angeben. Die verschiedenen Arten von Heaps sind: große Objektheaps (Large Object Heap, LOH), kleine Objektheaps (Small Object Heap, SOH) und fixierte Objektheaps (Pinned Object Heap, POH).

- Wenn Sie für eine der Einstellungen `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` oder `COMPLUS_GCHeapHardLimitPOHPercent` einen Wert angeben, müssen Sie auch einen Wert für `COMPLUS_GCHeapHardLimitSOHPercent` und `COMPLUS_GCHeapHardLimitLOHPercent` angeben. Andernfalls kann die Laufzeit nicht initialisiert werden.
- Diese Einstellungen werden ignoriert, wenn `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` und `COMPLUS_GCHeapHardLimitPOH` angegeben sind.
- Der Wert 1 bedeutet, dass die Garbage Collection 1 % des gesamten physischen Speichers für diesen Objektheap verwendet.
- Jeder Wert muss größer als 0 (null) und kleiner als 100 sein. Außerdem muss die Summe der drei Prozentwerte kleiner als 100 sein. Andernfalls tritt ein Fehler bei der Initialisierung der Laufzeit auf.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitSOHPercent` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitSOHPercent` | *Hexadezimalwert* | .NET 5.0 |

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitLOHPercent` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitLOHPercent` | *Hexadezimalwert* | .NET 5.0 |

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPOHPercent` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPLUS_GCHeapHardLimitPOHPercent` | *Hexadezimalwert* | .NET 5.0 |

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Beispielsweise würden bei einer Begrenzung des Heapverbrauchs auf 30 % die Werte für die JSON-Datei 30 und für die Umgebungsvariable 0x1E oder 1E betragen.

### <a name="high-memory-percent"></a>Hohe Speicherauslastung (Prozent)

Die Arbeitsspeicherauslastung wird durch den Prozentsatz des verwendeten physischen Speichers angegeben. Wenn die physische Arbeitsspeicherauslastung **90 %** erreicht, wird die Garbage Collection standardmäßig aggressiver, um vollständige, komprimierende Garbage Collection-Vorgänge durchzuführen, um Auslagerungsvorgänge zu vermeiden. Wenn die Arbeitsspeicherauslastung unter 90 % liegt, bevorzugt GC Hintergrundsammlungen für vollständige Garbage Collections, die kürzere Pausen aufweisen, aber die Gesamtheapgröße nicht wesentlich verringern. Auf Computern mit einer beträchtlichen Menge an Arbeitsspeicher (80 GB oder mehr) liegt der Standardwert für die Auslastung zwischen 90 % und 97 %.

Der Schwellenwert für hohe Arbeitsspeicherauslastung kann durch die Umgebungsvariable `COMPlus_GCHighMemPercent` oder die JSON-Konfigurationseinstellung `System.GC.HighMemoryPercent` angepasst werden. Wenn Sie die Heapgröße steuern möchten, sollten Sie den Schwellenwert anpassen. Beispielsweise ist es für den vorherrschenden Prozess auf einem Computer mit 64 GB Arbeitsspeicher sinnvoll, dass GC zu reagieren beginnt, wenn 10 % des Arbeitsspeichers verfügbar sind. Für kleinere Prozesse (z. B. für einen Prozess, der nur 1 GB Arbeitsspeicher verbraucht) kann GC bequem mit weniger als 10 % des verfügbaren Speichers ausgeführt werden. Für diese kleineren Prozesse sollten Sie den Schwellenwert auf einen höheren Wert festlegen. Wenn andererseits größere Prozesse kleinere Heapgrößen haben sollen (auch wenn genügend physischer Arbeitsspeicher verfügbar ist), ist die Herabsetzung dieses Schwellenwerts eine effektive Methode, mit der GC schneller reagieren kann, um den Heap zu komprimieren.

> [!NOTE]
> Bei Prozessen, die in einem Container ausgeführt werden, berücksichtigt GC den physischen Arbeitsspeicher basierend auf dem Containergrenzwert.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HighMemoryPercent` | *Dezimalwert* | .NET 5.0 |
| **Umgebungsvariable** | `COMPlus_GCHighMemPercent` | *Hexadezimalwert* | |

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Wenn Sie beispielsweise den Schwellenwert für hohe Arbeitsspeicherauslastung auf 75 % festlegen, würden die Werte für die JSON-Datei 75 und für die Umgebungsvariable 0x4B oder 4B betragen.

### <a name="retain-vm"></a>VM beibehalten

- Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden
- Standard: Segmente werden an das Betriebssystem zurückgegeben. Dies entspricht der Einstellung des Werts auf `false`.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false` – Freigabe an Betriebssystem<br/>`true` – in Standbymodus versetzen | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `RetainVMGarbageCollection` | `false` – Freigabe an Betriebssystem<br/>`true` – in Standbymodus versetzen | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_GCRetainVM` | `0` – Freigabe an Betriebssystem<br/>`1` – in Standbymodus versetzen | .NET Core 1.0 |

#### <a name="examples"></a>Beispiele

*runtimeconfig.json*-Datei:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a>Umfangreiche Seiten

- Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird
- Standard: Verwenden Sie keine großen Seiten, wenn eine feste Heapgrenze festgelegt ist. Dies entspricht der Einstellung des Werts auf `0`.
- Dies ist eine experimentelle Einstellung.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | – | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_GCLargePages` | `0` – deaktiviert<br/>`1` – aktiviert | .NET Core 3.0 |

## <a name="allow-large-objects"></a>Große Objekte zulassen

- Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)
- Standard: GC unterstützt Arrays, die größer als 2 GB sind. Dies entspricht der Einstellung des Werts auf `1`.
- Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | – | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_gcAllowVeryLargeObjects` | `1` – aktiviert<br/> `0` – deaktiviert | .NET Core 1.0 |
| **app.config für .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1` – aktiviert<br/> `0` – deaktiviert | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Großer Objektheapschwellenwert

- Gibt die Größe des Schwellenwerts in Bytes an, der bewirkt, dass Objekte auf den großen Objektheap (Large Object Heap, LOH) gehen
- Der Standardschwellenwert beträgt 85.000 Bytes.
- Der von Ihnen festgelegte Wert muss größer sein als der Standardschwellenwert.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.LOHThreshold` | *Dezimalwert* | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_GCLOHThreshold` | *Hexadezimalwert* | .NET Core 1.0 |
| **app.config für .NET Framework** | [GCLOHThreshold](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | *Dezimalwert* | .NET Framework 4.8 |

Beispiel:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> Wenn Sie die Option in *runtimeconfig.json* festlegen, geben Sie einen Dezimalwert an. Wenn Sie die Option als Umgebungsvariable festlegen, geben Sie einen Hexadezimalwert an. Wenn Sie beispielsweise die Größe eines Schwellenwerts auf 120.000 Bytes festlegen, würden die Werte für die JSON-Datei 120000 und für die Umgebungsvariable 0x1D4C0 oder 1D4C0 betragen.

## <a name="standalone-gc"></a>Eigenständige GC

- Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll
- Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | – | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
