---
title: -Nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764409f13a00f6d8a050bfbdd0f59e537a5ded3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-nostdlib-visual-basic"></a>-Nostdlib (Visual Basic)
Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-nostdlib` Option entfernt den automatischen Verweis auf die Assembly "System.dll" und verhindert, dass den Compiler die Datei "vbc.rsp" zu lesen. Die Datei "vbc.rsp", die sich im selben Verzeichnis wie die Datei Vbc.exe befindet, verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.  
  
> [!NOTE]
>  Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Assemblys werden immer auf die verwiesen wird.  
  
> [!NOTE]
>  Die `-nostdlib` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` ohne auf die Standardbibliotheken verweisen. Sie müssen festlegen, die `_MYTYPE` Konstante für bedingte Kompilierung auf die Zeichenfolge "Empty" Entfernen der `My` Objekt.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
