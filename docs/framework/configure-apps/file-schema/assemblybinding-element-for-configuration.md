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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155478"
---
# <a name="assemblybinding-element-for-configuration"></a>\<assemblyBinding>-Element für \<Konfiguration>

Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

Konfiguration &nbsp; &nbsp;>[** \<**](configuration-element.md) ** \<AssemblyBinding>**

## <a name="syntax"></a>Syntax

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>attribute

|           | Beschreibung |
| --------- | ----------- |
| **xmlns** | Erforderliches Attribut.<br><br>Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist. Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<Konfiguration>**](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-element"></a>Untergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | Gibt eine einzuschließende Konfigurationsdatei an. |

## <a name="remarks"></a>Bemerkungen

Das [** \<linkedConfiguration>-Element**](linkedconfiguration-element.md) vereinfacht die Verwaltung von Komponentenassemblys, indem Anwendungskonfigurationsdateien Assemblykonfigurationsdateien an bekannten Speicherorten einschließen können, anstatt die Konfigurationseinstellungen der Assembly zu duplizieren.

> [!NOTE]
> Das ** \<linkedConfiguration>-Element** wird für Anwendungen mit Windows-Manifesten nicht unterstützt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie eine Konfigurationsdatei auf der lokalen Festplatte eingeschlossen wird:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Konfigurationsdateischema für .NET Framework](index.md)
