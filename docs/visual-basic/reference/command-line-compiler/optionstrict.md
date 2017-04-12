---
title: / optionstrict | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionstrict
dev_langs:
- VB
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
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
ms.openlocfilehash: 0394d9c1f4c082271316829ef1d226bd97d136c9
ms.lasthandoff: 03/13/2017

---
# <a name="optionstrict"></a>/optionstrict
Erzwingt strikte Typsemantik um implizite typkonvertierungen einzuschränken.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Die `/optionstrict+` Option beschränkt die implizite Typumwandlung. Der Standardwert für diese Option ist `/optionstrict-`. Die `/optionstrict+` Option entspricht der `/optionstrict`. Sie können sowohl für freie Typsemantik verwenden.  
  
 `custom`  
 Erforderlich. Warnen, wenn die strenge Sprachsemantik nicht beachtet wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `/optionstrict+` gültig ist, können nur erweiternde Typumwandlungen implizit vorgenommen werden. Implizite einschränkende Typumwandlungen weisen z. B. eine `Decimal` mit einem ganzzahligen Typobjekt eingeben, werden als Fehler gemeldet.  
  
 Verwenden Sie zum Generieren von Warnungen für implizite einschränkende typkonvertierungen `/optionstrict:custom`. Verwendung `/nowarn:numberlist` , um bestimmte Warnungen ignorieren und `/warnaserror:numberlist` bestimmte Warnungen als Fehler behandelt.  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a>/ Optionstrict in der Visual Studio-IDE festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften.** Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die **Kompilieren** Registerkarte.  
  
3.  Ändern Sie den Wert in der **Option Strict** Feld.  
  
### <a name="to-set-optionstrict-programmatically"></a>So legen Sie/optionstrict programmgesteuert fest  
  
-   Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` strikte Typsemantik verwenden.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [/warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
