---
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 6c842abc1423e7ee0d98b71392e02410c6cf9172
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602723"
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
 Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten. Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.  
  
 Diese Option wird verwendet, wenn eine EXE-Datei kompiliert wird.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3. Ändern Sie die Eigenschaft **Startobjekt**.  
  
     Um diese Compileroption programmgesteuert festzulegen, sehen Sie sich <xref:VSLangProj80.ProjectProperties3.StartupObject%2A> an.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
