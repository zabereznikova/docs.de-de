---
title: '@ (Antwortdatei festlegen) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 6b993a6399eec4e203821109db153aadf246cbac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838117"
---
# <a name="-specify-response-file-visual-basic"></a>@ (Antwortdatei festlegen) (Visual Basic)
Gibt eine Datei mit Compileroptionen und Quellcodedateien zu kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Argumente  
 `response_file`  
 Erforderlich. Eine Datei, die Compileroptionen und Quellcodedateien kompilieren auflistet. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Der Compiler verarbeitet die Compileroptionen und Quellcodedateien in einer Antwortdatei angegeben wird, als ob sie in der Befehlszeile eingegeben worden.  
  
 Um mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen, wie die folgende aus.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile stehen. Eine einzelne Compileroption muss in einer Zeile angezeigt werden (kann nicht mehrere Zeilen umfassen). Antwortdateien können Kommentare, die mit beginnen enthalten die `#` Symbol.  
  
 Sie können in eine oder mehrere Antwortdateien angegebenen Optionen in der Befehlszeile angegebene Optionen kombinieren. Der Compiler verarbeitet die Befehlsoptionen an, sobald diese auftreten. Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien überschreiben. Im Gegensatz dazu überschreiben Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführten Optionen.  
  
 Visual Basic stellt die Datei "vbc.rsp", die sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet. Die Datei "vbc.rsp" ist standardmäßig enthalten, es sei denn, die `-noconfig` Option wird verwendet. Weitere Informationen finden Sie unter [- Noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  Die `@` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Zeilen stammen aus einer Beispielantwortdatei.  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `@` Option mit der Antwortdatei, die mit dem Namen `File1.rsp`.  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
