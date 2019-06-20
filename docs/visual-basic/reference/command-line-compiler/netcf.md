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
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268283"
---
# <a name="-netcf"></a>-netcf

Legt fest, den Compiler an, die .NET Compact Framework.

## <a name="syntax"></a>Syntax

```
-netcf
```

## <a name="remarks"></a>Hinweise

Die `-netcf` Option bewirkt, dass Visual Basic-Compiler auf .NET Compact Framework statt des vollständigen .NET Framework abzielt. Language-Funktionen, die nur im vollständigen .NET Framework ist deaktiviert.

Die `-netcf` Option dient für zu verwendenden [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md). Die Sprachfunktionen, die deaktiviert `-netcf` sind die gleichen Sprachfunktionen, die nicht vorhanden ist, in den Dateien, die angesprochenen `-sdkpath`.

> [!NOTE]
> Die `-netcf` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren. Die `-netcf` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.

Die `-netcf` Option ändert die folgenden Sprachfunktionen:

- Die [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) -Schlüsselwort, das Ausführung eines Programms beendet wird, ist deaktiviert. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Späte Bindung, in allen Formularen: ist deaktiviert. Kompilierungsfehler werden generiert, wenn bekannte Szenarios für spätes Binden gefunden werden. Das folgende Programm kompiliert und ausgeführt wird, ohne `-netcf` jedoch ein Fehler auftritt, zum Zeitpunkt der Kompilierung mit `-netcf`.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Die [automatisch](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) Modifizierer sind deaktiviert. Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Anweisung hat sich ebenfalls geändert `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`. Der folgende Code zeigt die Auswirkungen der `-netcf` auf eine Kompilierung.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Verwenden von Visual Basic 6.0-Schlüsselwörtern, die von Visual Basic entfernt wurden, generiert einen anderen Fehler bei der `-netcf` verwendet wird. Dies wirkt sich auf, die Fehlermeldungen für die folgenden Schlüsselwörter:

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a>Beispiel

Der folgende code kompiliert `Myfile.vb` mit .NET Compact Framework, mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von .NET Compact Framework auf dem Laufwerk C. In der Regel verwenden Sie die neueste Version von .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
