---
title: -keycontainer (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 944a9b4dbbed76f388642d67be9518343f750de5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-keycontainer-c-compiler-options"></a>-keycontainer (C#-Compileroptionen)
Gibt den Namen des kryptografischen Schlüsselcontainers an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-keycontainer:string  
```  
  
## <a name="arguments"></a>Argumente  
 `string`  
 Der Name des Containers mit dem Schlüssel für einen starken Namen  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Option **-keycontainer** verwendet wird, erstellt der Compiler eine teilbare Komponente, indem er einen öffentlichen Schlüssel aus dem angegebenen Container in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Geben Sie sn -k `file` in die Befehlszeile ein, um eine Schlüsseldatei zu generieren. „sn -i“ installiert das Schlüsselpaar im Container.  
  
 Wenn Sie mit der Option [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) kompilieren, wird der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly integriert, wenn Sie dieses Modul in eine Assembly mit [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) kompilieren.  
  
 Sie können diese Option auch als benutzerdefiniertes Attribut (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=nameWithType>) im Quellcode für ein beliebiges MSIL-Modul (Microsoft Intermediate Language) angeben.  
  
 Außerdem können Sie Ihre Verschlüsselungsinformationen mit [-keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) an den Compiler übergeben. Verwenden Sie [-delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md), wenn Sie den in das Assemblymanifest eingefügten Schlüssel verwenden, aber das Signieren der Assembly bis nach deren verzögern möchten, bis diese getestet wurde.  
  
 Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Diese Compileroption ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar.  
  
 Sie können mit <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> programmgesteuert auf diese Compileroption zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
