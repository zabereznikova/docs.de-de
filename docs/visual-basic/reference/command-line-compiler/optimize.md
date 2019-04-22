---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: eb84e0a7038e7ff8cb399ac7222b6ac1661b5bc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842160"
---
# <a name="-optimize"></a>-optimize
Aktiviert oder deaktiviert compileroptimierungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Die `-optimize-` Option deaktiviert compileroptimierungen. Die `-optimize+` Option Optimierungen aktiviert. Optimierungen sind standardmäßig deaktiviert.|  
  
## <a name="remarks"></a>Hinweise  
 Durch Compileroptimierungen wird Ihre Ausgabedatei kleiner, schneller und effizienter. Jedoch, weil Optimierungen führen zu neuanordnungen von Code in die Ausgabedatei `-optimize+` können Sie das Debuggen schwierig.  
  
 Alle Module mit generiert `-target:module` für eine Assembly auch verwenden muss `-optimize` Einstellungen wie die Assembly. Weitere Informationen finden Sie unter [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Sie können kombinieren die `-optimize` und `-debug` Optionen.  
  
|Um die set - optimieren Sie, in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />     <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern der **Optimierungen aktivieren** Kontrollkästchen.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
