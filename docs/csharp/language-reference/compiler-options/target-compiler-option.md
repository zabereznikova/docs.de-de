---
title: /target (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target
dev_langs:
- CSharp
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 615a0e2993dc78919008e8f9245504a486e2fb77
ms.lasthandoff: 03/13/2017

---
# <a name="target-c-compiler-options"></a>/target (C#-Compileroptionen)
Die Compileroption **/target** kann in einem von vier Formaten angegeben werden:  
  
 [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 So erstellen Sie eine EXE-Datei für [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)]-Anwendungen.  
  
 [/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 So erstellen Sie eine EXE-Datei.  
  
 [/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 So erstellen Sie eine Codebibliothek.  
  
 [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 So erstellen Sie ein Modul.  
  
 [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 So erstellen Sie ein Windows-Programm.  
  
 [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 So erstellen Sie eine WINMDOBJ-Zwischendatei.  
  
 Wenn Sie nicht **/target:module** angegeben haben, verursacht **/target**, dass ein .NET Framework-Assemblymanifest in einer Ausgabedatei platziert wird. Weitere Informationen finden Sie unter [Assemblys in der Common Language Runtime](https://msdn.microsoft.com/library/k3677y81) und [Häufige Attribute](http://msdn.microsoft.com/library/2f48a7ec-9683-4899-a1d2-a08be8fc558b).  
  
 Das Assemblymanifest wird in der ersten EXE-Ausgabedatei in der Kompilierung oder in der ersten DLL platziert, falls es keine EXE-Ausgabedatei gibt. In der folgenden Befehlszeile wird das Manifest z.B. in `1.exe` platziert:  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 Der Compiler erstellt nur ein Assemblymanifest pro Kompilierung. Informationen über alle Dateien in einer Kompilierung werden im Assemblymanifest platziert. Alle Ausgabedateien, außer diejenigen die mit **/target:module** erstellt wurden, können ein Assemblymanifest enthalten. Wenn mehrere Ausgabedateien in der Befehlszeile erstellt werden, kann nur ein Assemblymanifest erstellt werden, und es muss in die erste Ausgabedatei gehen, die in der Befehlszeile angegeben wurde. Unabhängig davon, was die erste Ausgabedatei ist (**/target:exe**, **/target:winexe**, **/target:library** oder **/target:module**), müssen alle anderen Ausgabedateien, die in der selben Kompilierung erzeugt wurden, Module sein (**/target:module**).  
  
 Wenn Sie eine Assembly erstellen, können Sie angeben, dass der ganze oder ein Teil des Codes mit dem Attribut <xref:System.CLSCompliantAttribute> CLS-kompatibel ist.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Weitere Informationen zum programmatischen Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB: Vorgehensweise: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [/subsystemversion (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)
