---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 32a5b0531851e9f8b4280e8d2908bfe2d011bf90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547722"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Bewirkt, dass den Compiler nicht automatisch auf die Standardbibliotheken verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-nostdlib` Option wird der automatische Verweis auf die Assembly "System.dll" entfernt, und verhindert, dass den Compiler die Datei "vbc.rsp" zu lesen. Die Datei "vbc.rsp", die sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet, verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.  
  
> [!NOTE]
>  Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll"-Assemblys werden immer auf die verwiesen wird.  
  
> [!NOTE]
>  Die `-nostdlib` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` ohne Verweis auf die standard-Bibliotheken. Sie müssen festlegen, die `_MYTYPE` Konstante für bedingte Kompilierung auf die Zeichenfolge "Empty" Entfernen der `My` Objekt.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
