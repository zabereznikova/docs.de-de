---
title: -langversion (C#-Compileroptionen)
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 030af5df222772b1e5a4d6f6946e59f4f2d1e1a9
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195799"
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
|8.0|Der Compiler akzeptiert nur Syntax, die in C# 8.0 oder niedriger enthalten ist. <sup id="TCS80">[CS80](#FCS80)</sup>|
|7.3|Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist <sup id="TCS73">[CS73](#FCS73)</sup>|
|7.2|Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist <sup id="TCS72">[CS72](#FCS72)</sup>|
|7.1|Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist <sup id="TCS71">[CS71](#FCS71)</sup>|
|7|Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist <sup id="TCS7">[CS7](#FCS7)</sup>|
|6|Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist <sup id="TCS6">[CS6](#FCS6)</sup>|
|5|Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist <sup id="TCS5">[CS5](#FCS5)</sup>|
|4|Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist <sup id="TCS4">[CS4](#FCS4)</sup>|
|3|Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist <sup id="TCS3">[CS3](#FCS3)</sup>|
|ISO-2|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist <sup id="TISO2">[ISO2](#FISO2)</sup>|
|ISO-1|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003-C# (1.0/1.2) enthalten ist <sup id="TISO1">[ISO1](#FISO1)</sup>|  

## <a name="remarks"></a>Anmerkungen

 Metadaten, auf die von Ihrer C#-Anwendung verwiesen wird, unterliegen nicht der Compileroption **-langversion**.  
  
 Da jede Version des C#-Compilers Erweiterungen der Sprachspezifikation enthält, bietet **-langversion** Ihnen nicht die gleiche Funktionalität wie die einer früheren Compilerversion.  

 Darüber hinaus sind die neue Syntax und die neuen Features nicht unbedingt an die spezifische Version des Frameworks gebunden, während C#-Versionsupdates für gewöhnlich mit den Releases von .NET Framework einhergehen. Während die neuen Features ein Compilerupdate erfordern, das mit der C#-Revision veröffentlicht wird, hat jedes Feature seine eigene mindestens erforderliche .NET-API- oder CLR-Anforderungen, durch die es auf abwärtskompatiblen Frameworks ausgeführt werden kann, indem NuGet-Pakete oder andere Bibliotheken einbezogen werden.
  
 Unabhängig von der verwendeten **-langversion**-Einstellung verwenden Sie die aktuelle Version der CLR, um Ihre EXE- oder DLL-Dateien zu erstellen. Davon ausgenommen sind Friend-Assemblys und [-moduleassemblyname (C#-Compileroption)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), die unter **-langversion:ISO-1** laufen.  

 Weitere Möglichkeiten zum Angeben der C#-Sprachversion finden Sie unter [Select the C# language version (Auswählen der C#-Sprachversion)](../configure-language-version.md).
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

### <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

|Version|Link|Beschreibung|
|-------|----|-----------|
|C# 7.0 und höher||aktuell nicht verfügbar|
|C# 6.0|[Link](../language-specification/index.md)|C#-Spezifikation Version 6, inoffizieller Entwurf: .NET Foundation|
|C# 5.0|[PDF herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|Standard ECMA-334, 5. Edition|
|C# 3.0|[DOC herunterladen](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|C#-Programmiersprachenspezifikation Version 3.0: Microsoft Corporation|
|C# 2.0|[PDF herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|Standard ECMA-334, 4. Edition|
|C# 1.2|[DOC herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|C#-Programmiersprachenspezifikation Version 1.2: Microsoft Corporation|
|C# 1.0|[DOC herunterladen](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|C#-Programmiersprachenspezifikation Version 1.0: Microsoft Corporation|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Mindestens erforderliche Compilerversion, die Sie benötigen, um alle Sprachfeatures zu unterstützen

[↩](#TCS80)<a name="FCS80">CS80</a>: Microsoft Visual Studio/Build Tools 2019, Version 16, oder .NET Core 3.0 SDK  
[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, Version 15.7  
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, Version 15.5  
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, Version 15.3  
[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017  
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015  
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 oder gebündelter .NET Framework 4.5-Compiler  
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 oder gebündelter .NET Framework 4.0-Compiler  
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 oder gebündelter .NET Framework 3.5-Compiler  
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 oder gebündelter .NET Framework 2.0-Compiler  
[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 oder gebündelter .NET Framework 1.0-Compiler  
