---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 70cef109e4f2947fb4e38b9bfd19433257cce136
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663507"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Gibt den Namen der Assembly an, zu der dieses Modul gehört.  
  
## <a name="syntax"></a>Syntax  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`assembly_name`|Der Name der Assembly, der dieses Modul eine angehören soll.|  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler verarbeitet die `-moduleassemblyname` Option nur, wenn die `-target:module` -Option wurde angegeben. Dies bewirkt, dass den Compiler ein Modul zu erstellen. Das Modul, das vom Compiler erstellten gilt nur für die Assembly mit angegebenen die `-moduleassemblyname` Option. Wenn Sie das Modul in einer anderen Assembly platzieren, werden Laufzeitfehler auftreten.  
  
 Die `-moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:  
  
- Ein Datentyp in das Modul benötigt Zugriff auf eine `Friend` Typ in einer referenzierten Assembly.  
  
- Die referenzierte Assembly wurde Friend-Assembly-Zugriff auf die Assembly gewährt werden, in dem das Modul erstellt wird.  
  
 Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Weitere Informationen zu Friend-Assemblys, finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md).  
  
> [!NOTE]
>  Die `-moduleassemblyname` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie an einer Eingabeaufforderung kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md)
