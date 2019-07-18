---
title: 'Vorgehensweise: Erstellen einer Einzeldateiassembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a409a93e5d84e96bbab13f2f6268d7f7ce6464ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634247"
---
# <a name="how-to-build-a-single-file-assembly"></a>Vorgehensweise: Erstellen einer Einzeldateiassembly

Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md). Sie können Befehlszeilencompiler oder Visual Studio verwenden, um eine Einzeldateiassembly zu erstellen. Standardmäßig erstellt der Compiler eine Assemblydatei mit einer „.exe“-Erweiterung.

> [!NOTE]
> Mit Visual Studio für C# und Visual Basic können nur Einzeldateiassemblys erstellt werden. Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder Visual C++ verwenden.

Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.

## <a name="to-create-an-assembly-with-an-exe-extension"></a>So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung

1. Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

     \<*compilerbefehl*> \<*modulname*>

     In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.

 Das folgende Beispiel erstellt eine Assembly namens `myCode.exe` aus einem Codemodul namens `myCode`.

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung und geben den Namen der Ausgabedatei an

1. Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

     \<*compilerbefehl*> **/out:**\<*dateiname*> \<*modulname*>

     In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.

 Das folgende Beispiel erstellt eine Assembly namens `myAssembly.exe` aus einem Codemodul namens `myCode`.

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a>Erstellen von Bibliothekassemblys
 Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek. Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.

### <a name="to-create-a-library-assembly"></a>So erstellen Sie eine Bibliotheksassembly

1. Geben Sie an der Eingabeaufforderung folgenden Befehl ein:

     \<*Compilerbefehl*> **/t:library** \<*Modulname*>

     In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren. Sie können auch andere Compileroptionen verwenden, z.B. die Option **-out:**.

 Das folgende Beispiel erstellt eine Bibliotheksassembly namens `myCodeAssembly.dll` aus einem Codemodul namens `myCode`.

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a>Siehe auch

- [Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md)
- [Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md)
- [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)
