---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a>/recurse
Kompiliert Quellcode Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnis oder das Projektverzeichnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir`  
 Dies ist optional. Das Verzeichnis, in dem die Suche beginnen soll. Wenn nicht angegeben wird, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `/recurse`. Wenn kein Dateiname der Ausgabe angegeben wird, basiert der Compiler den Namen der Ausgabedatei für den ersten Eingabedatei verarbeitet. Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert wird, wenn Sie in alphabetischer Reihenfolge angezeigt. Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `/out` Option.  
  
> [!NOTE]
>  Die `/recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert wird, alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis.  
  
```  
vbc *.vb  
```  
  
 Der folgende Code kompiliert wird, alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien in der `Test\ABC` Verzeichnis und alle Verzeichnisse darunter und generiert dann `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
