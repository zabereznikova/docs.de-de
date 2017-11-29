---
title: /moduleassemblyname
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9a5307970ac745b4f102d0008e64b985c00e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname"></a>/moduleassemblyname
Gibt den Namen der Assembly an, zu der dieses Modul gehört.  
  
## <a name="syntax"></a>Syntax  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`assembly_name`|Der Name der Assembly, der dieses Modul angehören soll.|  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler verarbeitet die `/moduleassemblyname` Option nur, wenn die `/target:module` -Option wurde angegeben. Dies bewirkt, dass der Compiler ein Modul zu erstellen. Das Modul, das vom Compiler erstellten gilt nur für die Assembly mit angegebenen die `/moduleassemblyname` Option. Wenn Sie das Modul in einer anderen Assembly platziert wird, werden zur Laufzeit Fehler auftreten.  
  
 Die `/moduleassemblyname` Option ist nur erforderlich, wenn Folgendes zutrifft:  
  
-   Ein Datentyp im Modul benötigt Zugriff auf eine `Friend` Typ in einer referenzierten Assembly.  
  
-   Die referenzierte Assembly wurde Friend-Assembly-Zugriff auf die Assembly erteilt werden, in dem das Modul integriert werden soll.  
  
 Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
> [!NOTE]
>  Die `/moduleassemblyname` Option ist nicht innerhalb der Visual Studio-Entwicklungsumgebung verfügbar, steht er nur, wenn Sie an einer Eingabeaufforderung kompilieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
