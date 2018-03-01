---
title: -nostdlib (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dd9d2b6a4a9c774aa339e840ad0020ee39cb10d3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (C#-Compileroptionen)
**-nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.  
  
 Wenn Sie **-nostdlib**nicht angeben, wird „mscorlib.dll“ in das Programm importiert (entspricht der Angabe von **-nostdlib-**). Die Angabe von **-nostdlib** entspricht der Angabe von **-nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen** .  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
