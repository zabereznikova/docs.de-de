---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005412"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option "`-nostdlib`" entfernt den automatischen Verweis auf die Assembly "System. dll" und verhindert, dass der Compiler die Datei "Vbc. rsp" liest. Die Datei "Vbc. rsp", die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet, verweist auf die häufig verwendeten .NET Framework Assemblys und importiert die Namespaces "`System`" und "`Microsoft.VisualBasic`".  
  
> [!NOTE]
> Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.  
  
> [!NOTE]
> Die Option "`-nostdlib`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `T2.vb`, ohne auf die Standardbibliotheken zu verweisen. Sie müssen die `_MYTYPE`-Konstante für bedingte Kompilierung auf die Zeichenfolge "Empty" festlegen, um das `My`-Objekt zu entfernen.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
