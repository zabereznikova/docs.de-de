---
title: -pdb (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: dc7ea6aae6aa429efdf1a2dca23a3d679cb21fb7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43418464"
---
# <a name="-pdb-c-compiler-options"></a>-pdb (C#-Compileroptionen)
Die Compileroption **-pdb** gibt den Namen und Speicherort der Debugsymboldatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name und Speicherort der Debugsymboldatei  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie [-debug (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) angeben, erstellt der Compiler eine PDB-Datei im gleichen Verzeichnis, in dem der Compiler die Ausgabedatei (.exe oder .dll) mit einem Dateinamen erstellt, der mit dem Namen der Ausgabedatei identisch ist.  
  
 Mit **-pdb** können Sie einen Dateinamen und -speicherort für die PDB-Datei angeben, die nicht dem Standard entsprechen.  
  
 Diese Compileroption kann weder in der Visual Studio-Entwicklungsumgebung festgelegt werden, noch kann sie programmgesteuert geändert werden.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `t.cs`, und erstellen Sie eine PDB-Datei mit dem Namen „tt.pdb“:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
