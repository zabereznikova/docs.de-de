---
title: <linkedConfiguration>-Element
ms.date: 03/30/2017
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087967"
---
# <a name="linkedconfiguration-element"></a>\<linkedConfiguration>-Element

Gibt eine einzuschließende Konfigurationsdatei an.

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a>Syntax

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>attribute

|           | BESCHREIBUNG |
| --------- | ----------- |
| **href**  | Erforderliches Attribut.<br><br>Die URL der einzuschließenden Konfigurationsdatei. Das einzige unterstützte Format für das **href** -Attribut ist `file://` . Lokale Dateien und UNC-Dateien werden unterstützt. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<assemblyBinding>** Gewisses](assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keine

## <a name="remarks"></a>Bemerkungen

Das- **\<linkedConfiguration>** Element vereinfacht die Wartung von Komponentenassemblys Wenn eine oder mehrere Anwendungen eine Assembly verwenden, die über eine Konfigurationsdatei an einem bekannten Speicherort verfügt, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden, das- **\<linkedConfiguration>** Element verwenden, um die Assemblykonfigurationsdatei einzuschließen, anstatt Konfigurationsinformationen direkt einzuschließen. Wenn die Komponentenassembly gewartet wird, werden bei der Aktualisierung der allgemeinen Konfigurationsdatei für alle Anwendungen, die die Assembly verwenden, aktualisierte Konfigurationsinformationen bereitgestellt.

> [!NOTE]
> Das- **\<linkedConfiguration>** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.

Die folgenden Regeln bestimmen die Verwendung von verknüpften Konfigurationsdateien:

- Die Einstellungen in den enthaltenen Konfigurationsdateien wirken sich nur auf die Richtlinie für die Lade Programme aus und werden nur vom Lade Modul verwendet. Die enthaltenen Konfigurationsdateien können andere Einstellungen als Bindungs Richtlinien aufweisen. diese Einstellungen haben jedoch keine Auswirkungen.

- Das einzige unterstützte Format für das- `href` Attribut ist `file://` . Lokale Dateien und UNC-Dateien werden unterstützt.

- Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.

- Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei zu bilden, ähnlich wie das Verhalten der `#include` Direktive in C/C++.

- Das **\<linkedConfiguration>** -Element ist nur in Anwendungs Konfigurationsdateien zulässig. es wird in *Machine. config*ignoriert.

- Zirkuläre Verweise werden erkannt und beendet. Das heißt, wenn die **\<linkedConfiguration>** Elemente einer Reihe von Konfigurationsdateien eine Schleife bilden, wird die Schleife erkannt und beendet.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte einschließen:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [**\<assemblyBinding>** Gewisses](assemblybinding-element-for-configuration.md)
- [Konfigurationsdatei Schema für die .NET Framework](index.md)
