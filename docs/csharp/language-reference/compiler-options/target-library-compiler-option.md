---
title: -target:library (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- CSharp
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f739d778e7bada7f34e42ecfd05364e8cae5d453
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="targetlibrary-c-compiler-options"></a>/target:library (C#-Compileroptionen)
Die Option **/target:library** veranlasst den Compiler, eine Dynamic Link Library (DLL) zu erstellen, anstatt einer ausführbaren Datei (EXE).  
  
## <a name="syntax"></a>Syntax  
  
```console  
/target:library  
```  
  
## <a name="remarks"></a>Hinweise  
 Die DLL wird mit der DLL-Dateiendung erstellt.  
  
 Sofern nicht anders mit der Option [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.  
  
 Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **/out** oder **/target:module** verwendet, um die DLL-Datei zu erstellen.  
  
 Beim Erstellen einer DLL-Datei ist eine [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode nicht erforderlich.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen zum programmatischen Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und `in.dll` wird erstellt:  
  
```console  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
