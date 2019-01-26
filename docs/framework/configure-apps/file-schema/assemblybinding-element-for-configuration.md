---
title: '&lt;AssemblyBinding&gt; -Element für &lt;Konfiguration&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 12065d8bc484f7bbf77ae18c67df1de0845167b2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083898"
---
# <a name="assemblybinding-element-for-configuration"></a>\<AssemblyBinding >-Element für \<Configuration >

Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<assemblyBinding>**

## <a name="syntax"></a>Syntax

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a>Attribut

|           | Beschreibung |
| --------- | ----------- |
| **xmlns** | Erforderliches Attribut.<br><br>Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist. Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert. |

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-element"></a>Untergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<linkedConfiguration>**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | Gibt eine einzuschließende Konfigurationsdatei an. |

## <a name="remarks"></a>Hinweise

Die [  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Element vereinfacht die Verwaltung von Komponentenassemblys-Konfigurationsrichtlinien Anwendungskonfigurationsdateien Assembly einschließen Konfigurationsdateien in bekannten Speicherorten, anstatt duplizieren Assembly-Konfigurationseinstellungen.

> [!NOTE]
> Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie eine Konfigurationsdatei auf der lokalen Festplatte einschließen:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
