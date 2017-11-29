---
title: /optioncompare
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6f602e0b0b23345bf1f5aae843bd44bd2642bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optioncompare"></a>/optioncompare
Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Hinweise  
 Können Sie angeben, `/optioncompare` in einer von zwei Formen: `/optioncompare:binary` binären Zeichenfolgenvergleichen verwendet und `/optioncompare:text` Textzeichenfolgenvergleiche verwendet. Standardmäßig verwendet der Compiler `/optioncompare:binary`.  
  
 In Microsoft Windows bestimmt die Codepage, die verwendet wird, die binäre Sortierreihenfolge. Eine typische binäre Sortierreihenfolge lautet wie folgt:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Textbasierte Zeichenfolgenvergleiche basieren auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt. Eine typische Textsortierreihenfolge lautet wie folgt:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>/ Optioncompare in der Visual Studio-IDE festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert in der **Option Compare** Feld.  
  
### <a name="to-set-optioncompare-programmatically"></a>So legen Sie/optioncompare programmgesteuert fest  
  
-   Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `ProjFile.vb` und binärer Zeichenfolgen.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
