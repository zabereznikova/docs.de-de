---
title: 'Vorgehensweise: Erstellen einer Einzeldateiassembly für das .NET Framework'
description: Erfahren Sie, wie Sie eine Einzeldateiassembly in .NET erstellen. Dabei kann es sich um eine Bibliothek (.dll) für .NET oder eine ausführbare Datei (.exe) handeln.
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: bdffa9417a7d52e9c825ca6455997b9bfa7408e4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271524"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a>Vorgehensweise: Erstellen einer Einzeldateiassembly für das .NET Framework

Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../standard/assembly/manifest.md). Sie können Befehlszeilencompiler oder Visual Studio verwenden, um eine Einzeldateiassembly für das .NET Framework zu erstellen. Standardmäßig erstellt der Compiler eine Assemblydatei mit einer *EXE*-Erweiterung.

> [!NOTE]
> Mit Visual Studio für C# und Visual Basic können nur Einzeldateiassemblys erstellt werden. Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder Visual C++ verwenden.

Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.

## <a name="create-an-assembly-with-an-exe-extension"></a>Erstellen einer Assembly mit einer EXE-Erweiterung

Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

\<*compiler command*> \<*module name*>

In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.

Im folgenden Beispiel wird die Assembly *myCode.exe* aus dem Codemodul `myCode` erstellt.

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Erstellen einer Assembly mit einer EXE-Erweiterung und Benennen der Ausgabedatei

Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

\<*compiler command*> **/out:** \<*file name*> \<*module name*>

In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.

Im folgenden Beispiel wird die Assembly *myAssembly.exe* aus dem Codemodul `myCode` erstellt.

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a>Erstellen von Bibliotheksassemblys

 Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek. Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.

Geben Sie über die Eingabeaufforderung den folgenden Befehl ein, um eine Bibliotheksassembly zu erstellen:

\<*compiler command*> **-t:library** \<*module name*>

In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren. Sie können auch andere Compileroptionen verwenden, z.B. die Option **-out:** .

Im folgenden Beispiel wird die Bibliotheksassembly *myCodeAssembly.dll* aus dem Codemodul `myCode` erstellt.

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](../../standard/assembly/create.md)
- [Mehrfachdateiassemblys](multifile-assemblies.md)
- [How to: Erstellen einer Mehrfachdateiassembly](build-multifile-assembly.md)
- [Programmieren mit Assemblys](../../standard/assembly/index.md)
