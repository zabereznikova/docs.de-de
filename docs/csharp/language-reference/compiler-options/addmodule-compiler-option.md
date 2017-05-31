---
title: -addmodule (C#-Compileroptionen) | Microsoft-Dokumentation
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 614dbefbb472ef2cd03fcb1ba7a44f08c450bf4a
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="addmodule-c-compiler-options"></a>/addmodule (C#-Compileroptionen)
Mit dieser Option wird ein Modul hinzugefügt, das mit dem Schalter „target:mocule“ in der aktuellen Kompilierung erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
```  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB: Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Mehrfachdateiassemblys](../../../framework/app-domains/multifile-assemblies.md)   
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
