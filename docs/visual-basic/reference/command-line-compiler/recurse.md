---
title: -Recurse
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 195d4b8f8e88d22e63c29ab9152399eb5c4a19df
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="-recurse"></a>-Recurse
Kompiliert Quellcode Dateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnis oder das Projektverzeichnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir`  
 Dies ist optional. Das Verzeichnis, in dem die Suche beginnen soll. Wenn nicht angegeben wird, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die Datei(en), nach der oder denen gesucht werden soll. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `-recurse`. Wenn kein Dateiname der Ausgabe angegeben wird, basiert der Compiler den Namen der Ausgabedatei für den ersten Eingabedatei verarbeitet. Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert wird, wenn Sie in alphabetischer Reihenfolge angezeigt. Aus diesem Grund ist es am besten, geben Sie eine Ausgabe mit der `-out` Option.  
  
> [!NOTE]
>  Die `-recurse` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis.  
  
```console
vbc *.vb  
```  
  
 Der folgende Befehl kompiliert alle Visual Basic-Dateien in den `Test\ABC` Verzeichnis und alle Verzeichnisse darunter und generiert dann `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
