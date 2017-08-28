---
title: -nowarn (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nowarn
dev_langs:
- CSharp
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3bae7e6d16c044b8f1aeba26de434cdf17479e82
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="nowarn-c-compiler-options"></a>/nowarn (C#-Compileroptionen)
Mit der Option **/nowarn** können Sie unterdrücken, dass der Compiler eine oder mehrere Warnungen anzeigt. Trennen Sie mehrere Warnnummern durch ein Komma.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a>Argumente  
 `number1`, `number2`  
 Warnnummer(n), die der Compiler unterdrücken soll.  
  
## <a name="remarks"></a>Hinweise  
 Sie sollten lediglich den numerischen Teil des Warnungsbezeichners angeben. Wenn Sie z.B. CS0028 unterdrücken wollen, könnten Sie `/nowarn:28` angeben.  
  
 Der Compiler wird automatisch die Warnnummern ignorieren, die an `/nowarn` übergeben wurden und in einer früheren Version gültig waren, jedoch aus dem Compiler entfernt worden sind. CS0679 war z.B. im Compiler in Visual Studio .NET 2002 gültig, wurde aber später entfernt.  
  
 Die folgenden Warnungen können nicht durch die Option `/nowarn` unterdrückt werden.  
  
-   Compilerwarnung (Stufe 1) CS2002  
  
-   Compilerwarnung (Stufe 1) CS2023  
  
-   Compilerwarnung (Stufe 1) CS2029  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt. Informationen finden Sie auf der [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Warnungen unterdrücken**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)   
 [C#-Compilerfehler](../../../csharp/language-reference/compiler-messages/index.md)

