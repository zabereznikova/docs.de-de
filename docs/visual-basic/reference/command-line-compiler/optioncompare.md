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
ms.openlocfilehash: ee130073b95dfbab5616a54c188b09fa92ccc930
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005362"
---
# <a name="-optioncompare"></a>-optioncompare
Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können `-optioncompare` in einer von zwei Formen angeben: `-optioncompare:binary`, um binäre Zeichen folgen Vergleiche zu verwenden, und `-optioncompare:text`, um Textzeichen folgen Vergleiche zu verwenden. Standardmäßig verwendet der Compiler `-optioncompare:binary`.  
  
 In Microsoft Windows bestimmt die aktuelle Codepage die binäre Sortierreihenfolge. Eine typische binäre Sortierreihenfolge lautet wie folgt:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Textbasierte Zeichen folgen Vergleiche basieren auf einer Text Sortierreihenfolge ohne Beachtung der Groß-/Kleinschreibung, die vom Gebiets Schema des Systems bestimmt wird Eine typische Text Sortierreihenfolge lautet wie folgt:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a>To Set-optioncompare in der Visual Studio-IDE  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Ändern Sie den Wert im Feld **Optionen vergleichen** .  
  
### <a name="to-set--optioncompare-programmatically"></a>So legen Sie-optioncompare Programm gesteuert fest  
  
- Siehe [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `ProjFile.vb` und verwendet binäre Zeichen folgen Vergleiche.  
  
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
