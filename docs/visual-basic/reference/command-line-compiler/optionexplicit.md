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
ms.openlocfilehash: 37ccd14dae0ebba2535185f2646e312d9bb70390
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266728"
---
# <a name="-optionexplicit"></a>-optionexplicit
Bewirkt, dass der Compiler Fehler meldet, wenn Variablen nicht deklariert werden, bevor sie verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Geben `-optionexplicit+` Sie an, dass eine explizite Deklaration von Variablen erforderlich ist. Die `-optionexplicit+` Option ist die Standardeinstellung `-optionexplicit`und entspricht der . Die `-optionexplicit-` Option ermöglicht die implizite Deklaration von Variablen.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die Quellcodedatei eine [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)enthält, überschreibt die Anweisung die `-optionexplicit` Befehlszeilen-Compilereinstellung.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>So legen Sie -optionexplicit in der Visual Studio-IDE fest  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Ändern Sie den Wert im Feld **Option Explicit.**  
  
## <a name="example"></a>Beispiel  
 Der folgende Code `-optionexplicit-` wird kompiliert, wenn er verwendet wird.  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Optionvergleichen](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [-optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [VB-Standard, Projekte, Dialogfeld "Optionen"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
