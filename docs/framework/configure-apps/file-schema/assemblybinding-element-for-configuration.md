---
title: <assemblyBinding>-Element für <configuration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155478"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding>-Element für \<configuration>

Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Syntax

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | BESCHREIBUNG |
| --------- | ----------- |
| **xmlns** | Erforderliches Attribut.<br><br>Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist. Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | BESCHREIBUNG |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-element"></a>Untergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | Gibt eine einzuschließende Konfigurationsdatei an. |

## <a name="remarks"></a>Bemerkungen

Das- [**\<linkedConfiguration>**](linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys, indem es Anwendungs Konfigurationsdateien ermöglicht, Assemblykonfigurationsdateien an bekannten Speicherorten einzufügen, anstatt Assemblykonfigurationseinstellungen zu duplizieren

> [!NOTE]
> Das- **\<linkedConfiguration>** Element wird nicht für Anwendungen mit parallelen Windows-Manifesten unterstützt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
