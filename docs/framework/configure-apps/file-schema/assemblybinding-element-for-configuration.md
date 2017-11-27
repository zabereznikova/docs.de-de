---
title: "&lt;AssemblyBinding&gt; -Element für &lt;Konfiguration&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2753e290af60d0dcf4efaa79ff3ffffbd7305c27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="assemblybinding-element-for-configuration"></a>\<AssemblyBinding >-Element für \<Configuration >

Gibt die Assemblybindungsrichtlinie auf Konfigurationsebene an.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;**\<AssemblyBinding >**

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

## <a name="child-element"></a>Untergeordnetes element

|     | Beschreibung |
| --- | ----------- |
| [**\<LinkedConfiguration >**](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) | Gibt eine einzuschließende Konfigurationsdatei an. |

## <a name="remarks"></a>Hinweise

Die [  **\<LinkedConfiguration >** ](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Element vereinfacht die Verwaltung der Komponentenassemblys Downloadfunktion Anwendungskonfigurationsdateien Assembly eingeschlossen in Konfigurationsdateien bekannte Speicherorte, anstatt duplizieren Assembly-Konfigurationseinstellungen.

> [!NOTE]
> Die  **\<LinkedConfiguration >** Element wird für Anwendungen mit Windows-Seite-an-Seite-Manifeste nicht unterstützt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird gezeigt, wie eine Konfigurationsdatei auf der lokalen Festplatte eingeschlossen wird:

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a>Siehe auch

[Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
