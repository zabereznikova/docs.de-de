---
description: -target:module (C#-Compileroptionen)
title: -target:module (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d8691e5e4477dbbe989344469b44382d5e0e7c8b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193607"
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (C#-Compileroptionen)

Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Bemerkungen  

 Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.  
  
 Eine Datei ohne Assemblymanifest kann nicht von der .NET-Runtime geladen werden. Allerdings kann eine solche Datei mithilfe von [-addmodule](./addmodule-compiler-option.md) in das Assemblymanifest integriert werden.  
  
 Wird mehr als ein Modul in einer einzigen Kompilierung erstellt, werden [interne](../keywords/internal.md) Typen in einem Modul für andere Module in der Kompilierung verfügbar. Wenn der Code in einem Modul auf `internal`-Typen in einem anderen Modul verweist, dann müssen beide Module mithilfe von **-addmodule** in ein Assemblymanifest aufgenommen werden.  
  
 Das Erstellen eines Moduls wird in der Visual Studio-Entwicklungsumgebung nicht unterstützt.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  

 Kompilieren Sie `in.cs`, und `in.netmodule` wird erstellt:  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [-target (C#-Compileroptionen)](./target-compiler-option.md)
- [C#-Compileroptionen](./index.md)
