---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4fcc5305985f5ba32b3e6ffb740c0611821215d3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097656"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)

Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  

 Die `-nostdlib`-Option entfernt den automatischen Verweis auf die System.dll-Assembly und verhindert, dass der Compiler die Vbc.rsp-Datei liest. Die Vbc.rsp-Datei, die sich im selben Verzeichnis wie die Vbc.exe-Datei befindet, verweist auf die häufig verwendeten .NET Framework-Assemblys und importiert die `System`- und `Microsoft.VisualBasic`-Namespaces.  
  
> [!NOTE]
> Auf die Assemblys „Mscorlib.dll“ und „Microsoft.VisualBasic.dll“ wird immer verwiesen.  
  
> [!NOTE]
> Diese Option `-nostdlib` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code kompiliert `T2.vb`, ohne dass auf die Standardbibliotheken verwiesen wird. Sie müssen die `_MYTYPE`-Konstante für bedingte Kompilierung auf die Zeichenfolge „Empty“ festlegen, um das `My`-Objekt zu entfernen.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [-noconfig](noconfig.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [Anpassen der verfügbaren Objekte in „My“](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
