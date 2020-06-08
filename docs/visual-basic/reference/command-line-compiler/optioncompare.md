---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ed9adc7cddd9eb204937b9819e4eeff176821e95
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400556"
---
# <a name="-optioncompare"></a>-optioncompare

Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.

## <a name="syntax"></a>Syntax

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a>Hinweise

Sie können `-optioncompare` in einer von zwei Formen angeben: `-optioncompare:binary`, um binäre Zeichenfolgenvergleiche zu verwenden, und `-optioncompare:text`, um Textzeichenfolgenvergleiche zu nutzen. Standardmäßig verwendet der Compiler `-optioncompare:binary`.

Unter Microsoft Windows bestimmt die aktuelle Codepage die binäre Sortierreihenfolge. Eine typische binäre Sortierreihenfolge sieht folgendermaßen aus:

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

Textbasierte Zeichenfolgenvergleiche basieren auf einer Textsortierreihenfolge, für die Groß-/Kleinschreibung nicht berücksichtigt wird und die durch das Gebietsschema Ihres Systems bestimmt wird. Eine typische Textsortierreihenfolge sieht folgendermaßen aus:

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>So legen Sie -optioncompare in der integrierten Entwicklungsumgebung in Visual Studio fest

1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie auf die Registerkarte **Kompilieren**.

3. Ändern Sie den Wert im Feld **Option Compare** entsprechend.

### <a name="to-set--optioncompare-programmatically"></a>So legen Sie -optioncompare programmgesteuert fest

Informationen hierzu finden Sie unter [Anweisung „Option Compare“](../../language-reference/statements/option-compare-statement.md).

## <a name="example"></a>Beispiel

Der folgende Code kompiliert `ProjFile.vb` und verwendet binäre Zeichenfolgenvergleiche.

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-optionexplicit](optionexplicit.md)
- [-optionstrict](optionstrict.md)
- [-optioninfer](optioninfer.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [Option Compare-Anweisung](../../language-reference/statements/option-compare-statement.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
