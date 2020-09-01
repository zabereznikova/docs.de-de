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
ms.openlocfilehash: 2c592d2fe001bb0908a06a6eb3287a39040b8715
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128451"
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (C#-Compileroptionen)
Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.  
  
 Eine Datei, die nicht über ein Assemblymanifest verfügt, kann nicht von der Common Language Runtime von .NET Framework geladen werden. Allerdings kann eine solche Datei mithilfe von [-addmodule](./addmodule-compiler-option.md) in das Assemblymanifest integriert werden.  
  
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
