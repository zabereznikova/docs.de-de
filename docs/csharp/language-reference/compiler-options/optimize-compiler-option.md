---
title: -optimize (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /optimize
dev_langs:
- CSharp
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
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
ms.openlocfilehash: 75a2b65c159e9adb0103765468182919ed6b0a23
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="optimize-c-compiler-options"></a>/optimize (C#-Compileroptionen)
Die Option **/optimize** aktiviert oder deaktiviert die vom Compiler durchgeführten Optimierungen, damit Ihre Ausgabedatei kleiner, schneller und effizienter wird.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/optimize[+ | -]  
```  
  
## <a name="remarks"></a>Hinweise  
 Außerdem weist **/optimize** die Common Language Runtime an, den Code zur Laufzeit zu optimieren.  
  
 Optimierungen sind standardmäßig deaktiviert. Geben Sie **/optimize+** an, um Optimierungen zu aktivieren.  
  
 Beim Erstellen eines Moduls, das von einer Assembly verwendet werden soll, verwenden Sie dieselben **/optimize**-Einstellungen wie die der Assembly.  
  
 **/o** ist die Kurzform von **/optimize**.  
  
 Es ist möglich, die Optionen **/ optimize** und [/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) zu kombinieren.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Ändern Sie die Eigenschaft **Code optimieren**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `t2.cs`, um Compileroptimierungen zu aktivieren:  
  
```console  
csc t2.cs /optimize  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

