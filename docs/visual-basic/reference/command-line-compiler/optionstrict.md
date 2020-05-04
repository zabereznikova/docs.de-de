---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583077"
---
# <a name="-optionstrict"></a>-optionstrict

Erzwingt eine strenge Typsemantik, um implizite Typkonvertierungen einzuschränken.

## <a name="syntax"></a>Syntax

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a>Argumente

`+` &#124; `-`  
Dies ist optional. Mit der Option `-optionstrict+` wird die implizite Typkonvertierung eingeschränkt. Der Standardwert für diese Option ist `-optionstrict-`. Die Option `-optionstrict+` ist identisch mit `-optionstrict`. Sie können beide Optionen für die restriktive Typsemantik verwenden.

`custom`  
Erforderlich. Warnen, wenn die strenge Sprachsemantik nicht beachtet wird.

## <a name="remarks"></a>Hinweise

Wenn die `-optionstrict+`-Option aktiviert ist, können nur erweiternde Typkonvertierungen implizit durchgeführt werden. Implizite einschränkende Typkonvertierungen, wie etwa das Zuweisen eines Objekts vom Typ `Decimal` zu einem Ganzzahltypobjekt, werden als Fehler gemeldet.

Verwenden Sie `-optionstrict:custom`, um Warnungen für implizite einschränkende Typkonvertierungen zu generieren. Verwenden Sie `-nowarn:numberlist`, um bestimmte Warnungen zu ignorieren, und `-warnaserror:numberlist`, um bestimmte Warnungen als Fehler zu behandeln.

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>So legen Sie -optionstrict in der integrierten Visual Studio-Entwicklungsumgebung fest

1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie auf die Registerkarte **Kompilieren**.

3. Ändern Sie den Wert im Feld **Option Strict**.

### <a name="to-set--optionstrict-programmatically"></a>So legen Sie -optionstrict programmgesteuert fest

Informationen hierzu finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).

## <a name="example"></a>Beispiel

Mit dem folgenden Code wird mithilfe der strengen Typsemantik `Test.vb` kompiliert:

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [-warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
