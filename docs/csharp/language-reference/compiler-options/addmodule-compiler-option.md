---
description: -addmodule (C#-Compileroptionen)
title: -addmodule (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150569"
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (C#-Compileroptionen)

Mit dieser Option wird ein Modul hinzugefügt, das mit dem Schalter „target:mocule“ in der aktuellen Kompilierung erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Argumente  

 `file`, `file2`  
 Eine Ausgabedatei, die Metadaten enthält. Die Datei kann kein Assemblymanifest enthalten. Trennen Sie die Dateinamen entweder mit einem Komma oder einem Semikolon, um mehr als eine Datei zu importieren.  
  
## <a name="remarks"></a>Bemerkungen  

 Alle Module, die mit **-addmodule** hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden. Das bedeutet, dass Sie zur Kompilierzeit ein beliebiges Modul in einem Verzeichnis angeben können, sich das Modul aber zur Laufzeit im Anwendungsverzeichnis befinden muss. Wenn sich das Modul zur Laufzeit nicht im Anwendungsverzeichnis befindet, wird eine <xref:System.TypeLoadException> ausgelöst.  
  
 `file` kann keine Assembly enthalten. Wenn die Ausgabedatei z.B. mit [-target:module](./target-module-compiler-option.md) erstellt wurde, können die Metadaten mit **-addmodule** importiert werden.  
  
 Wenn die Ausgabedatei mit einer anderen **-target**-Option als **-target:module** erstellt wurde, können die Metadaten nicht mit **-addmodule** importiert werden. Stattdessen werden sie mit [-reference](./reference-compiler-option.md) importiert.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung, da ein Projekt nicht auf ein Modul verweisen kann. Des Weiteren kann diese Compileroption nicht programmgesteuert geändert werden.  
  
## <a name="example"></a>Beispiel  

 Kompilieren Sie die Quelldatei `input.cs`, und fügen Sie Metadaten aus `metad1.netmodule` und `metad2.netmodule` hinzu, um `out.exe` zu erstellen:  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Mehrfachdateiassemblys](../../../framework/app-domains/multifile-assemblies.md)
- [How to: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/build-multifile-assembly.md)
