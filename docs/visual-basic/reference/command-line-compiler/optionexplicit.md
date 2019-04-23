---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 54d438541e8840e4394b24b20b4f394ff8cdb820
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332390"
---
# <a name="-optionexplicit"></a>-optionexplicit
Bewirkt, dass der Compiler Fehler melden, wenn Variablen nicht deklariert werden, bevor sie verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Geben Sie `-optionexplicit+` explizite Deklaration von Variablen erforderlich ist. Die `-optionexplicit+` Option ist die Standardeinstellung und entspricht dem `-optionexplicit`. Die `-optionexplicit-` Option ermöglicht die implizite Deklaration von Variablen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quellcodedatei enthält einen [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md), überschreibt die Anweisung die `-optionexplicit` Befehlszeilencompiler-Einstellung.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>-Optionexplicit in Visual Studio-IDE festlegen  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Ändern Sie den Wert in der **Option Explicit** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wird kompiliert, wenn `-optionexplicit-` verwendet wird.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
