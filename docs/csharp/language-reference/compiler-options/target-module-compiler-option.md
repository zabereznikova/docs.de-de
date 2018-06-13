---
title: -target:module (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d02a46390ca34b8063320df6ec237a00c0423c88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214253"
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (C#-Compileroptionen)
Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.  
  
 Eine Datei, die nicht über ein Assemblymanifest verfügt, kann nicht von der Common Language Runtime von .NET Framework geladen werden. Allerdings kann eine solche Datei mithilfe von [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) in das Assemblymanifest integriert werden.  
  
 Wird mehr als ein Modul in einer einzigen Kompilierung erstellt, werden [interne](../../../csharp/language-reference/keywords/internal.md) Typen in einem Modul für andere Module in der Kompilierung verfügbar. Wenn der Code in einem Modul auf `internal`-Typen in einem anderen Modul verweist, dann müssen beide Module mithilfe von **-addmodule** in ein Assemblymanifest aufgenommen werden.  
  
 Das Erstellen eines Moduls wird in der Visual Studio-Entwicklungsumgebung nicht unterstützt.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und `in.netmodule` wird erstellt:  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [-target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
