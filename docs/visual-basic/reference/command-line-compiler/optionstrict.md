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
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336082"
---
# <a name="-optionstrict"></a>-optionstrict
Erzwingt strenge Typsemantik, um implizite typkonvertierungen zu beschränken.  
  
## <a name="syntax"></a>Syntax  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Die `-optionstrict+` Option beschränkt die implizite typkonvertierung. Der Standardwert für diese Option ist `-optionstrict-`. Die `-optionstrict+` eignet identisch `-optionstrict`. Sie können sowohl für die freie Typsemantik verwenden.  
  
 `custom`  
 Erforderlich. Warnen Sie, wenn die strenge Sprachsemantik nicht beachtet wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `-optionstrict+` gültig ist, können nur erweiternde Konvertierungen implizit vorgenommen werden. Implizite einschränkende typkonvertierungen, wie das Zuweisen einer `Decimal` Geben Sie mit einem Integer-Typ-Objekt, das als Fehler gemeldet werden.  
  
 Verwenden Sie zum Generieren von Warnungen für implizite einschränkende typkonvertierungen `-optionstrict:custom`. Verwendung `-nowarn:numberlist` , um bestimmte Warnungen ignorieren und `-warnaserror:numberlist` bestimmte Warnungen als Fehler behandelt.  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a>-Optionstrict in Visual Studio-IDE festlegen  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften.**   
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Ändern Sie den Wert in der **Option Strict** Feld.  
  
### <a name="to-set--optionstrict-programmatically"></a>-Optionstrict programmgesteuert festgelegt.  
  
-   Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` strikte Typsemantik zu verwenden.  
  
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
- [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [VB-Standard, Projekte, Dialogfeld "Optionen"](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
