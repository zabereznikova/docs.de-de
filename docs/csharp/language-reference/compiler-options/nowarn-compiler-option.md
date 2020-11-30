---
description: -nowarn (C#-Compileroptionen)
title: -nowarn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 31a7ee5eacb2e7cd6b24c4a2276ce6e07fcc67e1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91194023"
---
# <a name="-nowarn-c-compiler-options"></a>-nowarn (C#-Compileroptionen)

Mit der Option **-nowarn** können Sie unterdrücken, dass der Compiler eine oder mehrere Warnungen anzeigt. Trennen Sie mehrere Warnnummern durch ein Komma.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a>Argumente  

 `number1`, `number2`  
 Warnnummer(n), die der Compiler unterdrücken soll.  
  
## <a name="remarks"></a>Bemerkungen  

 Sie sollten lediglich den numerischen Teil des Warnungsbezeichners angeben. Wenn Sie z.B. CS0028 unterdrücken wollen, könnten Sie `-nowarn:28` angeben.  
  
 Der Compiler wird automatisch die Warnnummern ignorieren, die an `-nowarn` übergeben wurden und in einer früheren Version gültig waren, jedoch aus dem Compiler entfernt worden sind. CS0679 war z.B. im Compiler in Visual Studio .NET 2002 gültig, wurde aber später entfernt.  
  
 Die folgenden Warnungen können nicht durch die Option `-nowarn` unterdrückt werden.  
  
- Compilerwarnung (Stufe 1) CS2002  
  
- Compilerwarnung (Stufe 1) CS2023  
  
- Compilerwarnung (Stufe 1) CS2029  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** für das Projekt. Informationen finden Sie auf der [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3. Ändern Sie die Eigenschaft **Warnungen unterdrücken**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [C#-Compilerfehler](../compiler-messages/index.md)
