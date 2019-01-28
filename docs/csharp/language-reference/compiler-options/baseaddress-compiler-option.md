---
title: -baseaddress (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 6ff29a7a204cb8f20f2f67946d5d1ed9c976e7aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694580"
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
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Ändern Sie die Eigenschaft **DLL-Basisadresse**.  
  
     Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
