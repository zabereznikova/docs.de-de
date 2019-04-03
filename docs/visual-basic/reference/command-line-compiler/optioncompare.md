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
ms.openlocfilehash: 0c23a74f91cd6666a0c4bef5ea67c58430c511b8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819415"
---
# <a name="-optioncompare"></a>-optioncompare
Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können angeben, `-optioncompare` in einem von zwei Formen: `-optioncompare:binary` binäre Zeichenfolgenvergleiche verwendet und `-optioncompare:text` Textzeichenfolgenvergleiche verwendet. Standardmäßig verwendet der Compiler `-optioncompare:binary`.  
  
 In Microsoft Windows bestimmt die aktuellen Codepage die binäre Sortierreihenfolge an. Eine typische binäre Sortierreihenfolge lautet wie folgt aus:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Vergleiche des String textbasierte basieren auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt. Eine typische Textsortierreihenfolge lautet wie folgt aus:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>-Optioncompare in Visual Studio-IDE festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert in der **Option Compare** Feld.  
  
### <a name="to-set--optioncompare-programmatically"></a>-Optioncompare programmgesteuert festgelegt.  
  
-   Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `ProjFile.vb` und binäre Zeichenfolgenvergleiche verwendet.  
  
```console
vbc -optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
