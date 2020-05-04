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
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716713"
---
# <a name="-netcf"></a>-netcf

Legt den Compiler als Ziel für .NET Compact Framework fest.

## <a name="syntax"></a>Syntax

```console
-netcf
```

## <a name="remarks"></a>Hinweise

Die Option `-netcf` bewirkt, dass der Visual Basic-Compiler .NET Compact Framework anstelle des vollständigen .NET Framework anzielt. Sprachfeatures, die nur im vollständigen .NET Framework vorhanden sind, sind deaktiviert.

Die `-netcf`-Option ist für die Verwendung mit [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) konzipiert. Bei den Sprachfeatures, die von `-netcf` deaktiviert werden, handelt es sich um die gleichen Sprachfeatures, die auch in Dateien nicht vorhanden sind, die mit `-sdkpath` angezielt werden.

> [!NOTE]
> Die Option `-netcf` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren. Die Option `-netcf` wird festgelegt, wenn ein Visual Basic-Geräteprojekt geladen wird.

Mit der Option `-netcf` werden die folgenden Sprachfeatures geändert:

- Die [End \<Schlüsselwort>-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md), die die Ausführung eines Programms beendet, ist deaktiviert. Das folgende Programm kann ohne `-netcf` kompiliert und ausgeführt werden, schlägt aber fehl, wenn `-netcf` zur Kompilierzeit enthalten ist.

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- Die späte Bindung ist in allen Formularen deaktiviert. Wenn späte Bindungen erkannt werden, werden Kompilierzeitfehler generiert. Das folgende Programm kann ohne `-netcf` kompiliert und ausgeführt werden, schlägt aber fehl, wenn `-netcf` zur Kompilierzeit enthalten ist.

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- Die Modifizierer [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) und [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) werden deaktiviert. Die Syntax der [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) wird zudem in `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]` geändert. Der folgende Code zeigt die Auswirkungen von `-netcf` auf eine Kompilierung.

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- Die Verwendung von Visual Basic 6.0-Schlüsselwörtern, die aus Visual Basic entfernt wurden, generiert bei Verwendung von `-netcf` einen anderen Fehler. Dieses Verhalten wirkt sich auf die Fehlermeldungen für die folgenden Schlüsselwörter aus:

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

Mit dem folgenden Code wird `Myfile.vb` mit .NET Compact Framework kompiliert. Dabei werden die Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ verwendet, die im Standardinstallationsverzeichnis von .NET Compact Framework auf Laufwerk C: gefunden werden. Normalerweise verwenden Sie die neueste Version von .NET Compact Framework.

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
