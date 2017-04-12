---
title: / optioncompare | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioncompare
dev_langs:
- VB
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 53dee5bb50e20204725f031e3e04f5c37c5b3f96
ms.lasthandoff: 03/13/2017

---
# <a name="optioncompare"></a>/optioncompare
Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optioncompare:{binary | text}  
```  
  
## <a name="remarks"></a>Hinweise  
 Können Sie angeben, `/optioncompare` in zwei Formen: `/optioncompare:binary` zur Verwendung von binären Zeichenfolgenvergleichen und `/optioncompare:text` zum Vergleichen von Zeichenfolgen verwenden. Standardmäßig verwendet der Compiler `/optioncompare:binary`.  
  
 In Microsoft Windows bestimmt die verwendete Codepage die binäre Sortierreihenfolge. Eine typische binäre Sortierreihenfolge lautet wie folgt:  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Textbasierte Zeichenfolgenvergleiche basieren auf einer Textsortierreihenfolge durch das Gebietsschema des Systems bestimmt. Eine normale Textsortierreihenfolge lautet wie folgt:  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### <a name="to-set-optioncompare-in-the-visual-studio-ide"></a>/ Optioncompare in der Visual Studio-IDE festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die **Kompilieren** Registerkarte.  
  
3.  Ändern Sie den Wert in der **Option Compare** Feld.  
  
### <a name="to-set-optioncompare-programmatically"></a>So legen Sie/optioncompare programmgesteuert fest  
  
-   Finden Sie unter [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert`rojFile.vb` und binärer Zeichenfolgen.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
