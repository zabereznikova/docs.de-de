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
ms.openlocfilehash: 5c0946b94bfe02d797d1a484088869375703eb6a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005307"
---
# <a name="-optionexplicit"></a>-optionexplicit
Bewirkt, dass der Compiler Fehler meldet, wenn keine Variablen deklariert sind, bevor Sie verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Geben Sie `-optionexplicit+` an, um eine explizite Deklaration von Variablen anzufordern. Die Option "`-optionexplicit+`" ist die Standardeinstellung und entspricht `-optionexplicit`. Die Option `-optionexplicit-` aktiviert die implizite Deklaration von Variablen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quell Code Datei eine [explizite Option-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)enthält, überschreibt die-Anweisung die Befehlszeilen-Compilereinstellung `-optionexplicit`.  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a>So legen Sie-optionexpliziten in der Visual Studio-IDE fest  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Ändern Sie den Wert im Feld **Option explizit** .  
  
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
