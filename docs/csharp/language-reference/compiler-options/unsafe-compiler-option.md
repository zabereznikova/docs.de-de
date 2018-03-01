---
title: -unsafe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b253a9ddafead823480f9893e809f17b6c22a179
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (C#-Compileroptionen)
Die Compileroption **-unsafe** ermöglicht das Kompilieren von Code, der das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu unsicherem Code finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaftenseite** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Wählen Sie die **Unsicheren Code zulassen**-Kontrollkästchen.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs` für den unsicheren Modus:  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
