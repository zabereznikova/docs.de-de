---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ee7cd1b8039a8d9312a8b058cc85c41ca536ed2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401939"
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler nicht automatisch auf die häufig verwendeten .NET Framework-Assemblys verweisen oder die Namespaces `System` und `Microsoft.VisualBasic` importieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-noconfig` weist den Compiler an, nicht mit der Datei „Vbc.rsp“ zu kompilieren, die sich im selben Verzeichnis wie die Datei „Vbc.exe“ befindet. Die Datei „Vbc.rsp“ verweist auf die gängigen .NET Framework-Assemblys und importiert die Namespaces `System` und `Microsoft.VisualBasic`. Der Compiler verweist implizit auf die System.dll-Assembly, sofern die Option `-nostdlib` nicht angegeben ist. Die Option `-nostdlib` weist den Compiler an, nicht mit der Datei „Vbc.rsp“ zu kompilieren oder automatisch auf die System.dll-Assembly zu verweisen.  
  
> [!NOTE]
> Auf die Assemblys „Mscorlib.dll“ und „Microsoft.VisualBasic.dll“ wird immer verwiesen.  
  
 Sie können die Datei „Vbc.rsp“ so ändern, dass zusätzliche Compileroptionen angegeben werden, die in jeder Kompilierung von „Vbc.exe“ enthalten sein sollten (außer wenn die `-noconfig`-Option angeben ist). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die an den Befehl `vbc` übergebenen Optionen zuletzt. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei „Vbc.rsp“.  
  
> [!NOTE]
> Die Option `-noconfig` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [-nostdlib (Visual Basic)](nostdlib.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [@ (Antwortdatei festlegen)](specify-response-file.md)
- [-reference (Visual Basic)](reference.md)
