---
title: -langversion (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: "33"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 11aab223ee70ff69d8c3470e747738bfe44540ea
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
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
|default|Der Compiler akzeptiert alle gültige Sprachsyntax, die es unterstützen kann. <sup id="TDefault">[Default](#FDefault)</sup>| 
|ISO-1|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003-C# (1.0/1.1) enthalten ist <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist <sup id="TCS7">[CS7](#FCS7)</sup>|
|latest|Der Compiler akzeptiert alle gültige Sprachsyntax, die es unterstützen kann. <sup id="TLatest">[latest](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Hinweise  
 Metadaten, auf die von Ihrer C#-Anwendung verwiesen wird, unterliegen nicht der Compileroption **-langversion**.  
  
 Da jede Version des C#-Compilers Erweiterungen der Sprachspezifikation enthält, bietet **-langversion** Ihnen nicht die gleiche Funktionalität wie die einer früheren Compilerversion.  
 
 Darüber hinaus sind die neue Syntax und die neuen Features nicht unbedingt an die spezifische Frameworkversion gebunden, während C#-Versionupdates für gewöhnlich mit den Hauptversionen von .NET Framework einhergehen. Während die neuen Features ein Compilerupdate erfordern, das mit der C#-Revision veröffentlicht wird, hat jedes Feature seine eigene mindestens erforderliche .NET-API- oder CLR-Anforderungen, durch die es auf abwärtskomptatiblen Frameworks ausgeführt werden kann, indem NuGet-Pakete oder andere Bibliotheken einbezogen werden.
  
 Unabhängig von der verwendeten **-langversion**-Einstellung verwenden Sie die aktuelle Version der CLR, um Ihre EXE- oder DLL-Dateien zu erstellen. Davon ausgenommen sind Friend-Assemblys und [-moduleassemblyname (C#-Compileroption)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), die unter **-langversion:ISO-1** laufen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaftenseite** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Modifizieren Sie die Eigenschaft **Sprachversion**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation
 [C#-Sprachspezifikationsreferenz](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation  
 C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Informationstechnologie – C#-Sprachspezifikation: ISO-Katalog  
 C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Informationstechnologie – C#-Sprachspezifikation: ISO-Katalog  
 C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 im PDF-Format: Frei verfügbare ISO-Standards  
 C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C#-Sprachspezifikation Version 3.0 : Microsoft Corporation  
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4. Edition    
 C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C#-Sprachspezifikation Version 5.0 : Microsoft Corporation  
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C#-Sprachspezifikation Version 6 – Inoffizieller Entwurf : .NET Foundation  
 C# 7.0 (aktuell nicht verfügbar)  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Mindestens erforderliche Compilerversion, die Sie benötigen, um alle Sprachfeatures zu unterstützen   
[↩](#TDefault)<a name="FDefault">Standard</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 oder gebündelter .NET Framework 1.0-Compiler     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 oder gebündelter .NET Framework 2.0-Compiler    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 oder gebündelter .NET Framework 3.5-Compiler    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 oder gebündelter .NET Framework 4.0-Compiler    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 oder gebündelter .NET Framework 4.5-Compiler    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Aktuell</a>: Microsoft Visual Studio Build Tools 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
