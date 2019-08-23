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
ms.openlocfilehash: a0b56ac66302f11c59c149197a84bb96691282a5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921015"
---
# <a name="linkedconfiguration-element"></a>\<linkedconfiguration > Element

Gibt eine einzuschließende Konfigurationsdatei an.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<assemblyBinding>** ](assemblybinding-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration>**

## <a name="syntax"></a>Syntax

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **href**  | Erforderliches Attribut.<br><br>Die URL der einzuschließenden Konfigurationsdatei. Das einzige unterstützte Format für das **href** - `file://`Attribut ist. Lokale Dateien und UNC-Dateien werden unterstützt. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [assemblyBinding-> Element  **\<** ](assemblybinding-element-for-configuration.md) | Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an. |

## <a name="child-elements"></a>Untergeordnete Elemente

None

## <a name="remarks"></a>Hinweise

Das  **\<linkedconfiguration->** Element vereinfacht die Wartung für Komponentenassemblys. Wenn eine oder mehrere Anwendungen eine Assembly verwenden, die eine Konfigurationsdatei an einem bekannten Speicherort enthält, können die Konfigurationsdateien der Anwendungen, die die Assembly verwenden, das  **\<linkedconfiguration->** Element verwenden, um das Assemblykonfigurationsdatei, anstatt Konfigurationsinformationen direkt einzubeziehen. Wenn die Komponentenassembly gewartet wird, werden bei der Aktualisierung der allgemeinen Konfigurationsdatei für alle Anwendungen, die die Assembly verwenden, aktualisierte Konfigurationsinformationen bereitgestellt.

> [!NOTE]
> **Das\<linkedconfiguration->** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.

Die folgenden Regeln bestimmen die Verwendung von verknüpften Konfigurationsdateien:

- Die Einstellungen in den enthaltenen Konfigurationsdateien wirken sich nur auf die Richtlinie für die Lade Programme aus und werden nur vom Lade Modul verwendet. Die enthaltenen Konfigurationsdateien können andere Einstellungen als Bindungs Richtlinien aufweisen. diese Einstellungen haben jedoch keine Auswirkungen.

- Das einzige unterstützte Format für `href` das- `file://`Attribut ist. Lokale Dateien und UNC-Dateien werden unterstützt.

- Es gibt keine Einschränkung für die Anzahl der verknüpften Konfigurationen pro Konfigurationsdatei.

- Alle verknüpften Konfigurationsdateien werden zusammengeführt, um eine Datei zu bilden, ähnlich wie `#include` das Verhalten der-C++Direktive in C/.

- **Das\<linkedconfiguration->** Element ist nur in Anwendungs Konfigurationsdateien zulässig. es wird in " *Machine. config*" ignoriert.

- Zirkuläre Verweise werden erkannt und beendet. Das heißt, wenn die  **\<linkedconfiguration->** Elemente einer Reihe von Konfigurationsdateien eine Schleife bilden, wird die Schleife erkannt und beendet.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die Konfigurationsdatei von der lokalen Festplatte einschließen:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [assemblyBinding-> Element  **\<** ](assemblybinding-element-for-configuration.md)
- [Konfigurationsdatei Schema für die .NET Framework](index.md)
