---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005371"
---
# <a name="-optimize"></a>-optimize
Aktiviert oder deaktiviert Compileroptimierungen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Die Option "`-optimize-`" deaktiviert Compileroptimierungen. Mit der Option "`-optimize+`" werden Optimierungen ermöglicht. Optimierungen sind standardmäßig deaktiviert.|  
  
## <a name="remarks"></a>Hinweise  
 Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter. Da Optimierungen jedoch dazu führen, dass Code in der Ausgabedatei neu angeordnet wird, kann das Debuggen durch `-optimize+` erschwert werden.  
  
 Alle Module, die mit `-target:module` für eine Assembly generiert werden, müssen die gleichen `-optimize`-Einstellungen wie die Assembly verwenden. Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Sie können die Optionen `-optimize` und `-debug` kombinieren.  
  
|So legen Sie "-optimieren" in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />     <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren** .|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb` und aktiviert Compileroptimierungen.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
