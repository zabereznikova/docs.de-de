---
title: Garbage-Collector-Konfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, um zu konfigurieren, wie der Garbage Collector Arbeitsspeicher für .NET Core-Apps verwaltet.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: ec575bdd17c8a7c290673b7085074bbba94cedef
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102865"
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

### <a name="systemgcservercomplus_gcserver"></a>System.GC.Server/COMPlus_gcServer

- Konfiguriert, ob die Anwendung die Arbeitsstation-GC oder die Server-GC verwendet
- Standard: Arbeitsstation-Garbage-Collection (`false`)

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false` – Arbeitsstation<br/>`true` – Server | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `ServerGarbageCollection` | `false` – Arbeitsstation<br/>`true` – Server | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_gcServer` | `0` – Arbeitsstation<br/>`1` – Server | .NET Core 1.0 |
| **app.config für .NET Framework** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false` – Arbeitsstation<br/>`true` – Server |  |

### <a name="examples"></a>Beispiele

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

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a>System.GC.Concurrent/COMPlus_gcConcurrent

- Konfiguriert, ob die (gleichzeitige) Hintergrund-GC aktiviert ist
- Standard: Aktiviert (`true`)
- Weitere Informationen finden Sie unter [Hintergrund der Garbage Collection](../../standard/garbage-collection/background-gc.md).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `ConcurrentGarbageCollection` | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_gcConcurrent` | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC | .NET Core 1.0 |
| **app.config für .NET Framework** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true` – Hintergrund-GC<br/>`false` – nicht gleichzeitige GC |  |

### <a name="examples"></a>Beispiele

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

Verwenden Sie die in diesem Abschnitt beschriebenen Einstellungen, um die Speicher- und Prozessorauslastung des Garbage Collectors zu verwalten.

Weitere Informationen zu einigen dieser Einstellungen finden Sie im Blogeintrag [Mittelweg zwischen Arbeitsstation- und Server-GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).

### <a name="systemgcheapcountcomplus_gcheapcount"></a>System.GC.HeapCount/COMPlus_GCHeapCount

- Schränkt die Anzahl von Heaps ein, die vom Garbage Collector erstellt werden
- Gilt nur für die Garbage Collection des Servers.
- Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) aktiviert ist (Standardeinstellung), ordnet die Einstellung für die Heapanzahl den ersten `n` Prozessoren `n` GC-Heaps/-Threads zu. (Verwenden Sie die Einstellungen [AffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) oder [AffinitizeRanges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges), um genau anzugeben, welche Prozessoren zugeordnet werden sollen.)
- Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird mit dieser Einstellung die Anzahl der GC-Heaps eingeschränkt.
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

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a>System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask

- Gibt die genauen Prozessoren an, die Garbage-Collector-Threads verwenden sollen
- Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.
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

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a>System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges

- Gibt die Liste der Prozessoren an, die für Garbage-Collector-Threads verwendet werden sollen
- Diese Einstellung ähnelt [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), abgesehen davon, dass Sie mehr als 64 Prozessoren angeben können.
- Stellen Sie für Windows-Betriebssysteme der Prozessornummer oder dem Prozessorbereich die entsprechende [CPU-Gruppe](/windows/win32/procthread/processor-groups) voran, z. B. „0:1-10,0:12,1:50-52,1:70“.
- Wenn die [GC-Prozessoraffinität](#systemgcnoaffinitizecomplus_gcnoaffinitize) deaktiviert ist, wird diese Einstellung ignoriert.
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

### <a name="complus_gccpugroup"></a>COMPlus_GCCpuGroup

- Konfiguriert, ob der Garbage Collector [CPU-Gruppen](/windows/win32/procthread/processor-groups) verwendet

  Wenn ein 64-Bit-Windows-Computer über mehrere CPU-Gruppen verfügt, d. h. mehr als 64 Prozessoren vorhanden sind, dann wird durch die Aktivierung dieses Elements die Garbage Collection in allen CPU-Gruppen erweitert. Der Garbage Collector verwendet alle Kerne zum Erstellen und Ausgleichen von Heaps.

- Gilt nur für Garbage Collection des Servers auf 64-Bit-Windows-Betriebssystemen.
- Standard: Deaktiviert (`0`)
- Weitere Informationen finden Sie unter [Optimieren der CPU-Konfiguration für GC auf Computern mit mehr als 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) im Blog von Maoni Stephens.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_GCCpuGroup` | `0` – deaktiviert<br/>`1` – aktiviert | .NET Core 1.0 |
| **app.config für .NET Framework** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false` – deaktiviert<br/>`true` – aktiviert |  |

> [!NOTE]
> Aktivieren Sie die Option [Thread_UseAllCpuGroups-Element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md), um die Common Language Runtime (CLR) so zu konfigurieren, dass auch Threads aus dem Threadpool in allen CPU-Gruppen verteilt werden. Für .NET Core-Apps können Sie diese Option aktivieren, indem Sie den Wert der Umgebungsvariablen `COMPlus_Thread_UseAllCpuGroups` auf `1` setzen.

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a>System.GC.NoAffinitize/COMPlus_GCNoAffinitize

- Gibt an, ob Garbage-Collection-Threads Prozessoren *zugeordnet* werden sollen. Einen GC-Thread zuzuordnen, bedeutet, dass dieser nur auf der jeweiligen CPU ausgeführt werden kann. Für jeden GC-Thread wird ein Heap erstellt.
- Gilt nur für die Garbage Collection des Servers.
- Standard: Garbage-Collection-Threads werden Prozessoren zugeordnet (`false`).

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

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a>System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit

- Gibt die maximale Commitgröße in Bytes für den GC-Heap und die GC-Buchhaltung an
- Diese Einstellung gilt nur für 64-Bit-Computer.
- Der Standardwert, der nur in bestimmten Fällen gilt, ist der größere Wert von 20 MB oder 75 % der Speichergrenze für den Container. Der Standardwert wird in folgenden Fällen angewendet:

  - Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.
  - [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) ist nicht festgelegt.

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

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a>System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent

- Gibt den zulässigen GC-Heapverbrauch in Prozent des gesamten physischen Speichers an.
- Wenn außerdem [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) festgelegt ist, wird diese Einstellung ignoriert.
- Diese Einstellung gilt nur für 64-Bit-Computer.
- Wenn der Prozess in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben wurde, wird der Prozentsatz als Prozentsatz dieses Arbeitsspeicherlimits berechnet.
- Der Standardwert, der nur in bestimmten Fällen angewendet wird, beträgt weniger als 20 MB oder 75 % des Arbeitsspeicherlimits für den Container. Der Standardwert wird in folgenden Fällen angewendet:

  - Der Prozess wird in einem Container ausgeführt, für den ein Arbeitsspeicherlimit angegeben ist.
  - [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) ist nicht festgelegt.

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

### <a name="systemgcretainvmcomplus_gcretainvm"></a>System.GC.RetainVM/COMPlus_GCRetainVM

- Konfiguriert, ob Segmente, die gelöscht werden sollen, zur späteren Verwendung auf eine Standbyliste aufgenommen oder an das Betriebssystem zurückgegeben werden
- Standard: Segmente werden an das Betriebssystem zurückgegeben (`false`).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false` – Freigabe an Betriebssystem<br/>`true` – in Standbymodus versetzen | .NET Core 1.0 |
| **MSBuild-Eigenschaft** | `RetainVMGarbageCollection` | `false` – Freigabe an Betriebssystem<br/>`true` – in Standbymodus versetzen | .NET Core 1.0 |
| **Umgebungsvariable** | `COMPlus_GCRetainVM` | `0` – Freigabe an Betriebssystem<br/>`1` – in Standbymodus versetzen | .NET Core 1.0 |

### <a name="examples"></a>Beispiele

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

### <a name="complus_gclargepages"></a>COMPlus_GCLargePages

- Gibt an, ob umfangreiche Seiten verwendet werden sollen, wenn eine feste Heapgrenze festgelegt wird
- Standard: Deaktiviert (`0`)
- Dies ist eine experimentelle Einstellung.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_GCLargePages` | `0` – deaktiviert<br/>`1` – aktiviert | .NET Core 3.0 |

## <a name="large-objects"></a>Große Objekte

### <a name="complus_gcallowverylargeobjects"></a>COMPlus_gcAllowVeryLargeObjects

- Konfiguriert die Garbage-Collector-Unterstützung auf 64-Bit-Plattformen für Arrays mit einer Gesamtgröße von mehr als 2 Gigabytes (GB)
- Standard: Aktiviert (`1`)
- Diese Option wird in einer zukünftigen Version von .NET möglicherweise veraltet sein.

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_gcAllowVeryLargeObjects` | `1` – aktiviert<br/> `0` – deaktiviert | .NET Core 1.0 |
| **app.config für .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1` – aktiviert<br/> `0` – deaktiviert | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Großer Objektheapschwellenwert

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a>System.GC.LOHThreshold/COMPlus_GCLOHThreshold

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

### <a name="complus_gcname"></a>COMPlus_GCName

- Gibt einen Pfad zu der Bibliothek an, die den Garbage Collector enthält, der von der Runtime geladen werden soll
- Weitere Informationen finden Sie unter [Entwurf eines eigenständigen GC-Ladeprogramms](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).

| | Einstellungsname | Werte | Eingeführt in Version |
| - | - | - | - |
| **runtimeconfig.json** | Nicht zutreffend | Nicht zutreffend | Nicht zutreffend |
| **Umgebungsvariable** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
