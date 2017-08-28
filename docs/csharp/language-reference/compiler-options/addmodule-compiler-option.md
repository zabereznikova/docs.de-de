---
title: -addmodule (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
dev_langs:
- CSharp
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 79fdad111b1f059e6a3b00e393ea2474f71db947
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="addmodule-c-compiler-options"></a>/addmodule (C#-Compileroptionen)
Mit dieser Option wird ein Modul hinzugefügt, das mit dem Schalter „target:mocule“ in der aktuellen Kompilierung erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Argumente  
 `file`, `file2`  
 Eine Ausgabedatei, die Metadaten enthält. Die Datei kann kein Assemblymanifest enthalten. Trennen Sie die Dateinamen entweder mit einem Komma oder einem Semikolon, um mehr als eine Datei zu importieren.  
  
## <a name="remarks"></a>Hinweise  
 Alle Module, die mit **/addmodule** hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden. Das bedeutet, dass Sie zur Kompilierzeit ein beliebiges Modul in einem Verzeichnis angeben können, sich das Modul aber zur Laufzeit im Anwendungsverzeichnis befinden muss. Wenn sich das Modul zur Laufzeit nicht im Anwendungsverzeichnis befindet, wird eine <xref:System.TypeLoadException> ausgelöst.  
  
 `file` kann keine Assembly enthalten. Wenn die Ausgabedatei z.B. mit [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) erstellt wurde, können seine Metadaten mit **/addmodule** importiert werden.  
  
 Wenn die Ausgabedatei mit einer **/target**-Option, die nicht **/target:module** ist, erstellt wurde, können seine Metadaten nicht mit **/addmodule** importiert werden. Stattdessen werden sie mit [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) importiert.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung, da ein Projekt nicht auf ein Modul verweisen kann. Des Weiteren kann diese Compileroption nicht programmgesteuert geändert werden.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie die Quelldatei `input.cs`, und fügen Sie Metadaten aus `metad1.netmodule` und `metad2.netmodule` hinzu, um `out.exe` zu erstellen:  
  
```console  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)   
 [Mehrfachdateiassemblys](../../../framework/app-domains/multifile-assemblies.md)   
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)

