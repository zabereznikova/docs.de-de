---
title: <codeBase>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: bd170b817c5ccc337711f8f79968653c29f3eda4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252744"
---
# <a name="codebase-element"></a>\<CodeBase >-Element

Gibt an, wo die Common Language Runtime eine Assembly finden kann.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly->** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<codeBase>**

## <a name="syntax"></a>Syntax

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`href`|Erforderliches Attribut.<br /><br /> Gibt die URL an, unter der die Laufzeit die angegebene Version der Assembly finden kann.|
|`version`|Erforderliches Attribut.<br /><br /> Gibt die Version der Assembly an, auf die sich die Codebasis bezieht. Das Format einer Assemblyversionsnummer ist *Hauptversion. neben Version. Build. Revision*.|

## <a name="version-attribute"></a>Versions Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|Gültige Werte für jeden Teil der Versionsnummer sind 0 bis 65535.|Nicht zutreffend.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`buildproviders`|Definiert eine Auflistung von Buildanbietern, die zum Kompilieren benutzerdefinierter Ressourcendateien verwendet werden. Sie können eine beliebige Anzahl von Buildanbietern verwenden.|
|`compilation`|Konfiguriert alle von ASP.NET verwendeten Kompilierungs Einstellungen.|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`System.web`|Gibt das Stammelement für den ASP.NET-Konfigurationsabschnitt an.|

## <a name="remarks"></a>Hinweise

Damit die Laufzeit die  **\<CodeBase->** Einstellung in einer Computer Konfigurationsdatei oder Herausgeber Richtlinien Datei verwendet, muss die Datei auch die Assemblyversion umleiten. Anwendungs Konfigurationsdateien können eine Codebasis-Einstellung aufweisen, ohne die Assemblyversion umzuleiten. Nachdem Sie bestimmt haben, welche Assemblyversion verwendet werden soll, wendet die Laufzeit die Codebasis-Einstellung aus der Datei an, die die Version bestimmt. Wenn keine Codebasis angegeben ist, testet die Runtime die Assembly auf die übliche Weise.

Wenn die Assembly einen starken Namen hat, kann sich die Codebasis-Einstellung im lokalen Intranet oder im Internet befinden. Wenn die Assembly eine private Assembly ist, muss die Codebasis-Einstellung ein Pfad relativ zum Anwendungsverzeichnis sein.

Für Assemblys ohne starken Namen wird die Version ignoriert, und das Lade Modul verwendet die \<erste Darstellung der CodeBase-> in \<dependentAssembly >. Wenn in der Anwendungs Konfigurationsdatei ein Eintrag vorhanden ist, der die Bindung an eine andere Assembly umleitet, hat die Umleitung Vorrang, auch wenn die Assemblyversion nicht mit der Bindungs Anforderung identisch ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie angegeben wird, wo die Common Language Runtime eine Assembly finden kann.

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Festlegen des Speicherortes einer Assembly](../../specify-assembly-location.md)
- [So sucht Common Language Runtime nach Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md)
