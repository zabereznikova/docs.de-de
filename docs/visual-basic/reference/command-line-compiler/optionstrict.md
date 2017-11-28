---
title: /optionstrict
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f783cc5b20c4fe6d7812a05a66cbc4cdfc0b9395
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optionstrict"></a>/optionstrict
Erzwingt strenge Typsemantik um implizite typkonvertierungen zu beschränken.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Die `/optionstrict+` Option beschränkt die implizite typkonvertierung. Der Standardwert für diese Option ist `/optionstrict-`. Die `/optionstrict+` Option entspricht dem `/optionstrict`. Sie können sowohl für freie Typsemantik verwenden.  
  
 `custom`  
 Erforderlich. Warnhinweis anzeigen Sie, wenn die strenge Sprachsemantik nicht beachtet wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `/optionstrict+` ist aktiviert, können nur erweiternde Konvertierungen implizit vorgenommen werden. Implizite einschränkende typkonvertierungen, z. B. das Zuweisen einer `Decimal` Geben Sie mit einem Integer-Typ-Objekt, das als Fehler gemeldet werden.  
  
 Verwenden Sie zum Generieren von Warnungen für implizite einschränkende typkonvertierungen `/optionstrict:custom`. Verwendung `/nowarn:numberlist` , um bestimmte Warnungen ignorieren und `/warnaserror:numberlist` auf bestimmte Warnungen als Fehler behandelt werden sollen.  
  
### <a name="to-set-optionstrict-in-the-visual-studio-ide"></a>/ Optionstrict in der Visual Studio-IDE festlegen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften.** Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3.  Ändern Sie den Wert in der **Option Strict** Feld.  
  
### <a name="to-set-optionstrict-programmatically"></a>So legen Sie/optionstrict programmgesteuert fest  
  
-   Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Test.vb` strikte Typsemantik zu verwenden.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)  
 [/ warnaserror (Visual Basic)](../../../visual-basic/reference/command-line-compiler/warnaserror.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
