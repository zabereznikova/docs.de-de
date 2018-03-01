---
title: -baseaddress (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4e4b4964d587bfdf95949ebd6f0028a25988c2ea
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-baseaddress-c-compiler-options"></a>-baseaddress (C#-Compileroptionen)
Mit der Option **-baseaddress** können Sie die bevorzugte Basisadresse angeben, an der eine DLL geladen werden soll. Weitere Informationen zu Situationen und Gründen für die Verwendung dieser Option finden Sie in [Larry Ostermans WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).  
  
## <a name="syntax"></a>Syntax  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Argumente  
 `address`  
 Die Basisadresse für die DLL. Diese Adresse kann als dezimale, hexadezimale oder oktale Zahl angegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die Standard-Basisadresse für eine DLL-Datei wird durch die Common Language Runtime von .NET Framework festgelegt.  
  
 Denken Sie daran, dass das niederwertige Wort in dieser Adresse gerundet wird. Wenn Sie zum Beispiel 0x11110001 angeben, wird dies auf 0x11110000 gerundet.  
  
 Um das Signieren für eine DLL abzuschließen, verwenden Sie „SN.EXE“ mit der Option „-R“.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaftenseite** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Ändern Sie die Eigenschaft **DLL-Basisadresse**.  
  
     Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
