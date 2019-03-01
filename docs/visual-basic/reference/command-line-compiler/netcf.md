---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 2a359f4bf44887e7c7bc5422d485988b24f45600
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976472"
---
# <a name="-netcf"></a>-netcf
Legt für den Compiler [!INCLUDE[Compact](~/includes/compact-md.md)] als Ziel fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-netcf` Option bewirkt, dass Visual Basic-Compiler zum Ziel der [!INCLUDE[Compact](~/includes/compact-md.md)] anstelle der vollständigen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Language-Funktionen, die nur im vollständigen vorliegt [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ist deaktiviert.  
  
 Die `-netcf` Option dient für zu verwendenden [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Die Sprachfunktionen, die deaktiviert `-netcf` sind die gleichen Sprachfunktionen, die nicht vorhanden ist, in den Dateien, die angesprochenen `-sdkpath`.  
  
> [!NOTE]
>  Die `-netcf` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren. Die `-netcf` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.  
  
 Die `-netcf` Option ändert die folgenden Sprachfunktionen:  
  
-   Die [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) -Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]  
  
-   Späte Bindung, in allen Formularen: ist deaktiviert. Kompilierungsfehler werden generiert, wenn bekannte Szenarios für spätes Binden gefunden werden. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.  
  
     [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]  
  
-   Die [automatisch](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert. Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Anweisung hat sich ebenfalls geändert `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Der folgende Code zeigt die Auswirkungen der `-netcf` auf eine Kompilierung.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   Verwenden von Visual Basic 6.0-Schlüsselwörtern, die von Visual Basic entfernt wurden, generiert einen anderen Fehler bei der `-netcf` verwendet wird. Dies wirkt sich auf, die Fehlermeldungen für die folgenden Schlüsselwörter:  
  
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
 Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], verwenden die Versionen der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von der [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C. Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
