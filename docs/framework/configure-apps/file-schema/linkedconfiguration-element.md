---
title: '&lt;LinkedConfiguration&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: dffff7fefa80f420e61045b21b0e0c1a170e2911
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="linkedconfiguration-element"></a>\<LinkedConfiguration >-Element

Gibt eine einzuschließende Konfigurationsdatei an.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;[**\<AssemblyBinding >**](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<LinkedConfiguration >**

## <a name="syntax"></a>Syntax

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **href**  | Erforderliches Attribut.<br><br>Die URL der Konfigurationsdatei enthalten. Das einzige Format, unterstützt die **Href** -Attribut ist `file://`. Lokale Dateien und UNC-Dateien werden unterstützt. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<AssemblyBinding >** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Die  **\<LinkedConfiguration >** Element vereinfacht die Wartung für Komponentenassemblys. Wenn eine oder mehrere Anwendungen eine Assembly, die über eine Konfigurationsdatei, die sich in einem bekannten Speicherort befinden verwenden, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden die  **\<LinkedConfiguration >** Element, das die Konfigurationsdatei für die Assembly, anstatt direkt einschließlich der Konfigurationsinformationen enthalten. Wenn der Komponentenassembly gewartet wird, enthält die Konfigurationsdatei mit allgemeinen aktualisieren aktualisierte Konfigurationsinformationen für alle Anwendungen, die Assembly zu verwenden.

> [!NOTE]
> Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.

Die folgenden Regeln bestimmen die Verwendung von verknüpfte Konfigurationsdateien:

- Die Einstellungen in Konfigurationsdateien enthalten nur betreffen Lademodul Bindungsrichtlinie und werden nur vom Ladeprogramm verwendet. Die enthalten Konfigurationsdateien können andere als die Bindung von Richtlinien zu verwenden, aber diese Einstellungen nicht haben keine Auswirkung.

- Das einzige Format, unterstützt die `href` -Attribut ist `file://`. Lokale Dateien und UNC-Dateien werden unterstützt.

- Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.

- Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei bilden die `#include` in C/C++-Richtlinie.

- Die  **\<LinkedConfiguration >** Element ist nur in Anwendungskonfigurationsdateien zulässig; sie wird ignoriert, *"Machine.config"*.

- Zirkelverweise werden erkannt und beendet. D. h., wenn die  **\<LinkedConfiguration >** Elemente einer Reihe von Konfigurationsdateien bilden eine Schleife, die Schleife wird erkannt und beendet.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte enthalten:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Siehe auch

[**\<AssemblyBinding >** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)   
[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
