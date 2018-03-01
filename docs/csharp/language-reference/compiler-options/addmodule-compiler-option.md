---
title: -addmodule (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db440b58862e372e443c9c51961b0c3cc2dd211e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
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
  
## <a name="remarks"></a>Hinweise  
 Alle Module, die mit **-addmodule** hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden. Das bedeutet, dass Sie zur Kompilierzeit ein beliebiges Modul in einem Verzeichnis angeben können, sich das Modul aber zur Laufzeit im Anwendungsverzeichnis befinden muss. Wenn sich das Modul zur Laufzeit nicht im Anwendungsverzeichnis befindet, wird eine <xref:System.TypeLoadException> ausgelöst.  
  
 `file` kann keine Assembly enthalten. Wenn die Ausgabedatei z.B. mit [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) erstellt wurde, können die Metadaten mit **-addmodule** importiert werden.  
  
 Wenn die Ausgabedatei mit einer anderen **-target**-Option als **-target:module** erstellt wurde, können die Metadaten nicht mit **-addmodule** importiert werden. Stattdessen werden sie mit [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) importiert.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung, da ein Projekt nicht auf ein Modul verweisen kann. Des Weiteren kann diese Compileroption nicht programmgesteuert geändert werden.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie die Quelldatei `input.cs`, und fügen Sie Metadaten aus `metad1.netmodule` und `metad2.netmodule` hinzu, um `out.exe` zu erstellen:  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
 [Mehrfachdateiassemblys](../../../framework/app-domains/multifile-assemblies.md)  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
