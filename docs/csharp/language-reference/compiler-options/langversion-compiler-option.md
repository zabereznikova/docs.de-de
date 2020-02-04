---
title: -langversion (C#-Compileroptionen)
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920371"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (C#-Compileroptionen)

Führt dazu, dass der Compiler nur Syntax akzeptiert, die in der ausgewählten C#-Sprachspezifikation enthalten ist.

## <a name="syntax"></a>Syntax

```console
-langversion:option
```

## <a name="arguments"></a>Argumente

`option`

Folgende Werte sind gültig:

|Option|Bedeutung|
|------------|-------------|
|preview|Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Vorschauversion, die unterstützen werden kann.|
|latest|Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Version (einschließlich Nebenversionen), die unterstützen werden kann.|
|latestMajor|Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Hauptversion, die unterstützen werden kann.|
|8.0|Der Compiler akzeptiert nur Syntax, die in C# 8.0 oder niedriger enthalten ist.|
|7.3|Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist.|
|7.2|Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist.|
|7.1|Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist.|
|7|Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist.|
|6|Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist.|
|5|Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist.|
|4|Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist.|
|3|Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist.|
|ISO-2|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist.|
|ISO-1|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003 C# (1.0/1.2) enthalten ist.|

Die Standardsprachversion ist vom Zielframework für Ihre Anwendung und der installierten Version des SDK oder von Visual Studio abhängig. Diese Regeln werden im Artikel zum [Konfigurieren der Sprachversion](../configure-language-version.md#defaults) definiert.

## <a name="remarks"></a>Hinweise

Metadaten, auf die von Ihrer C#-Anwendung verwiesen wird, unterliegen nicht der Compileroption **-langversion**.

Da jede Version des C#-Compilers Erweiterungen der Sprachspezifikation enthält, bietet **-langversion** Ihnen nicht die gleiche Funktionalität wie die einer früheren Compilerversion.

Darüber hinaus sind die neue Syntax und die neuen Features nicht unbedingt an die spezifische Version des Frameworks gebunden, während C#-Versionsupdates für gewöhnlich mit den Releases von .NET Framework einhergehen. Während die neuen Features ein Compilerupdate erfordern, das mit der C#-Revision veröffentlicht wird, hat jedes Feature seine eigene mindestens erforderliche .NET-API- oder CLR-Anforderungen, durch die es auf abwärtskompatiblen Frameworks ausgeführt werden kann, indem NuGet-Pakete oder andere Bibliotheken einbezogen werden.

Unabhängig von der verwendeten **-langversion**-Einstellung verwenden Sie die aktuelle Version der CLR, um Ihre EXE- oder DLL-Dateien zu erstellen. Davon ausgenommen sind Friend-Assemblys und [-moduleassemblyname (C#-Compileroption)](./moduleassemblyname-compiler-option.md), die unter **-langversion:ISO-1** laufen.

Weitere Möglichkeiten zum Angeben der C#-Sprachversion finden Sie im Artikel zum [Auswählen der C#-Sprachversion](../configure-language-version.md).

Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

|Version|Link|Beschreibung|
|-------|----|-----------|
|C# 7.0 und höher||aktuell nicht verfügbar|
|C# 6.0|[Link](/dotnet/csharp/language-reference/language-specification/introduction)|C#-Spezifikation Version 6, inoffizieller Entwurf: .NET Foundation|
|C# 5.0|[PDF herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|Standard ECMA-334, 5. Edition|
|C# 3.0|[DOC herunterladen](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|C#-Programmiersprachenspezifikation Version 3.0: Microsoft Corporation|
|C# 2.0|[PDF herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|Standard ECMA-334, 4. Edition|
|C# 1.2|[DOC herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|C#-Programmiersprachenspezifikation Version 1.2: Microsoft Corporation|
|C# 1.0|[DOC herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|C#-Programmiersprachenspezifikation Version 1.0: Microsoft Corporation|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a>Mindestens erforderliche SDK-Version, die erforderlich ist, um alle Sprachfeatures zu unterstützen

In der folgenden Tabelle sind die Mindestversionen des SDK mit dem C#-Compiler aufgeführt, der die entsprechende Sprachversion unterstützt:

|C#-Version|Mindestversion des SDK|
|----------|-------------------|
|C# 8.0| Microsoft Visual Studio/Build Tools 2019, Version 16.3, oder .NET Core 3.0 SDK |
|C# 7.3| Microsoft Visual Studio/Build Tools 2017, Version 15.7 |
|C# 7.2| Microsoft Visual Studio/Build Tools 2017, Version 15.5 |
|C# 7.1| Microsoft Visual Studio/Build Tools 2017, Version 15.3 |
|C# 7.0| Microsoft Visual Studio/Build Tools 2017 |
|C# 6| Microsoft Visual Studio/Build Tools 2015 |
|C# 5| Microsoft Visual Studio/Build Tools 2012 oder gebündelter .NET Framework 4.5-Compiler |
|C# 4| Microsoft Visual Studio/Build Tools 2010 oder gebündelter .NET Framework 4.0-Compiler |
|C# 3| Microsoft Visual Studio/Build Tools 2008 oder gebündelter .NET Framework 3.5-Compiler |
|C# 2| Microsoft Visual Studio/Build Tools 2005 oder gebündelter .NET Framework 2.0-Compiler |
|C# 1.0/1.2 | Microsoft Visual Studio/Build Tools .NET 2002 oder gebündelter .NET Framework 1.0-Compiler |

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
