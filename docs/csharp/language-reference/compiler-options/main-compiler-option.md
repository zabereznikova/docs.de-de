---
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5f1d06bf408f13a78df503ab10fe3c57b4ff68a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-main-c-compiler-options"></a>-main (C#-Compileroptionen)
Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a>Argumente  
 `class`  
 Der Typ, der die **Main**-Methode enthält.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.  
  
 Diese Option wird verwendet, wenn eine EXE-Datei kompiliert wird.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Startobjekt**.  
  
     Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
