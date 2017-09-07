---
title: -target:module (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:module
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
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
ms.openlocfilehash: 23c91fe0e4002ebf4c002eb4e0c7e25020fed356
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="targetmodule-c-compiler-options"></a>/target:module (C#-Compileroptionen)
Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/target:module  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig weist die Ausgabedatei, die durch Kompilieren mit dieser Option erstellt wird, eine Dateierweiterung .NETMODULE auf.  
  
 Eine Datei, die nicht über ein Assemblymanifest verfügt, kann nicht von der Common Language Runtime von .NET Framework geladen werden. Allerdings kann eine solche Datei in das Assemblymanifest mithilfe von [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) integriert werden.  
  
 Wird mehr als ein Modul in einer einzigen Kompilierung erstellt, werden [interne](../../../csharp/language-reference/keywords/internal.md) Typen in einem Modul für andere Module in der Kompilierung verfügbar. Wenn der Code in einem Modul auf `internal`-Typen in einem anderen Modul verweist, dann müssen beide Module in ein Assemblymanifest aufgenommen werden, mithilfe von **/addmodule**.  
  
 Das Erstellen eines Moduls wird in der Visual Studio-Entwicklungsumgebung nicht unterstützt.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und `in.netmodule` wird erstellt:  
  
```console  
csc /target:module in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)

