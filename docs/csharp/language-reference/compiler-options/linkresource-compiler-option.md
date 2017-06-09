---
title: -linkresource (C#-Compileroption) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /linkresource
dev_langs:
- CSharp
helpviewer_keywords:
- /linkresource compiler option [C#]
- linkres compiler option [C#]
- /linkres compiler option [C#]
- -linkres compiler option [C#]
- -linkresource compiler option [C#]
- linkresource compiler option [C#]
ms.assetid: 440c26c2-77c1-4811-a0a3-57cce3f5fc96
caps.latest.revision: 17
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
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: d9a3bc4dc4b51d6170c67f9d2f95b6805497b31c
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="linkresource-c-compiler-options"></a>/linkresource (C#-Compileroptionen)
Erstellt einen Link zur .NET Framework-Ressource in der Ausgabedatei Die Ressourcendateien wird nicht in die Ausgabedatei eingefügt. Dies ist ein Unterschied zur Option [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md), die eine Ressourcendatei in die Ausgabedatei einbettet.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/linkresource:filename[,identifier[,accessibility-modifier]]  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten  
  
 `identifier` (optional)  
 Der logische Name der Ressource. Der Name, mit dem die Ressource geladen wird. Der Standardwert ist der Name der Datei.  
  
 `accessibility-modifier` (optional)  
 Barrierefreiheit der Ressource: öffentlich oder privat. Der Standardwert ist „öffentlich“.  
  
## <a name="remarks"></a>Hinweise  
 Verknüpfte Ressourcen sind standardmäßig in der Assembly öffentlich, wenn sie mit den C#-Compiler erstellt werden. Geben Sie `private` als Modifizierer der Barrierefreiheit an. Außer `public` und `private` sind keine anderen Modifizierer zulässig.  
  
 **/linkresource** erfordert eine der [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md)-Optionen, die nicht **/target:module** sind.  
  
 Wenn es sich bei `filename` um eine .NET Framework-Ressourcendatei handelt, die beispielsweise von [resgen.exe](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) oder in der Entwicklungsumgebung erstellt wurde, ist der Zugriff mit Membern im <xref:System.Resources>-Namespace möglich. Weitere Informationen finden Sie unter <xref:System.Resources.ResourceManager?displayProperty=fullName>. Verwenden Sie für alle anderen Ressourcen die `GetManifestResource`*-Methoden in der <xref:System.Reflection.Assembly>-Klasse, um zur Laufzeit auf die Ressource zuzugreifen.  
  
 Die in `filename` angegebene Datei kann jedes Format haben. Sie können z.B. eine native DLL zu einem Teil der Assembly machen, sodass sie im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly darauf zugegriffen werden kann. Das zweite Beispiel zeigt die dazu erforderliche Vorgehensweise. Sie können dasselbe aber auch im Assemblylinker vornehmen. Das dritte Beispiel zeigt die dazu erforderliche Vorgehensweise. Weitere Informationen finden Sie unter [Al.exe (Assembly Linker-Tool)](https://msdn.microsoft.com/library/c405shex) und [Arbeiten mit Assemblys und dem globalen Assemblycache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).  
  
 **/linkres** ist die verkürzte Form der Option **/linkresource**.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs` und verknüpfen Sie die Ressourcendatei `rf.resource`:  
  
```console  
csc /linkresource:rf.resource in.cs  
```  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `A.cs` in eine DLL, verknüpfen Sie eine native DLL „n.dll“, und fügen Sie die Ausgabe in den globalen Assemblycache (GAC) ein. In diesem Beispiel befinden sich sowohl „a.dll“ als auch „n.dll“ im GAC.  
  
```console  
csc /linkresource:N.dll /t:library A.cs  
gacutil -i A.dll  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das Gleiche wie im vorherigen Beispiel erreicht, allerdings mithilfe von Assemblylinkeroptionen.  
  
```console  
csc /t:module A.cs  
al /out:A.dll A.netmodule /link:N.dll   
gacutil -i A.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Al.exe (Assembly Linker-Tool)](https://msdn.microsoft.com/library/c405shex)   
 [Arbeiten mit Assemblys und dem globalen Assemblychache](../../../framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [NIB: Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
