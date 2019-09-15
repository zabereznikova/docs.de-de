---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: dc4c0336c8a67a1b4e70f71ba5f5406da1fbb2ff
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972376"
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
|`assembly_name`|Der Name der Assembly, zu der dieses Modul gehört.|  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler verarbeitet die `-moduleassemblyname` Option nur, wenn `-target:module` die Option angegeben wurde. Dies bewirkt, dass der Compiler ein Modul erstellt. Das vom Compiler erstellte Modul ist nur für die mit der `-moduleassemblyname` Option angegebene Assembly gültig. Wenn Sie das Modul in einer anderen Assembly platzieren, treten Laufzeitfehler auf.  
  
 Die `-moduleassemblyname` Option wird nur benötigt, wenn Folgendes zutrifft:  
  
- Ein Datentyp im Modul benötigt Zugriff auf einen `Friend` Typ in einer Assembly, auf die verwiesen wird.  
  
- Die Assembly, auf die verwiesen wird, hat Friend-Assembly-Zugriff auf die Assembly erteilt, in der das Modul erstellt wird.  
  
 Weitere Informationen zum Erstellen eines Moduls finden Sie unter [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Weitere Informationen zu Friend-Assemblys finden Sie unter [Friend](../../../standard/assembly/friend.md)-Assemblys  
  
> [!NOTE]
> Die `-moduleassemblyname` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über eine Eingabeaufforderung kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../framework/app-domains/build-multifile-assembly.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Friend-Assemblys](../../../standard/assembly/friend.md)
