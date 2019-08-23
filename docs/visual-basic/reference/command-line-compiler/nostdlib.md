---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964353"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  
 Mit `-nostdlib` der-Option wird der automatische Verweis auf die Assembly "System. dll" entfernt und verhindert, dass der Compiler die Datei "Vbc. rsp" liest. Die Datei "Vbc. rsp", die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet, verweist auf die häufig verwendeten .NET Framework `System` Assemblys und importiert die Namespaces und. `Microsoft.VisualBasic`  
  
> [!NOTE]
> Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.  
  
> [!NOTE]
> Die `-nostdlib` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wird kompiliert `T2.vb` , ohne auf die Standardbibliotheken zu verweisen. Sie müssen die Konstante `_MYTYPE` für die bedingte Kompilierung auf die Zeichenfolge "Empty" festlegen `My` , um das Objekt zu entfernen.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
