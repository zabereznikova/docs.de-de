---
title: -netcf
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82a0adc9e821df3a789cf19e798d4bad9e9a69e3
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-netcf"></a>-netcf
Legt für den Compiler [!INCLUDE[Compact](~/includes/compact-md.md)] als Ziel fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-netcf` -Option bewirkt, dass die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler Ziel der [!INCLUDE[Compact](~/includes/compact-md.md)] anstelle der vollständigen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Language-Funktionen, die nur in den vollständigen vorliegt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ist deaktiviert.  
  
 Die `-netcf` ist bei Verwendung der Option mit [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Die Sprachfunktionen von deaktiviert `-netcf` sind die gleichen Sprachfunktionen, die in den Dateien, die als Ziel für "nicht vorhanden" `-sdkpath`.  
  
> [!NOTE]
>  Die `-netcf` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren. Die `-netcf` Option wird festgelegt, wenn ein [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Geräteprojekt geladen ist.  
  
 Die `-netcf` Option ändert die folgenden Sprachfunktionen:  
  
-   Die [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` dagegen ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   Späte Bindung, in allen Formularen: ist deaktiviert. Kompilierungsfehler werden generiert, wenn erkannte späte Bindung Szenarien auftreten. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` dagegen ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   Die [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert. Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) -Anweisung wird auch geändert, um `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Der folgende Code zeigt die Auswirkung des `-netcf` auf eine Kompilierung.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Mit Visual Basic 6.0-Schlüsselwörtern, die aus entfernt wurden [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generiert einen anderen Fehler bei der `-netcf` verwendet wird. Dies wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter:  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" in das Standardverzeichnis für die Installation der gefunden die [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C. Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
