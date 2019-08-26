---
title: -nowin32manifest (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8820410bfdbce2f9986605f37af4d14957471126
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602715"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest (C#-Compileroptionen)
Verwenden Sie die Option **-nowin32manifest**, um den Compiler anzuweisen, kein Anwendungsmanifest in die ausführbare Datei einzubetten.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Anmerkungen  
 Wenn diese Option verwendet wird, unterliegt die Anwendung der Virtualisierung unter Windows Vista, es sei denn, Sie stellen ein Anwendungsmanifest in einer Win32-Ressourcendatei oder einem späteren Buildschritt bereit.  
  
 Legen Sie diese Option in Visual Studio auf der Seite **Application Property** (Anwendungseigenschaft) fest, indem Sie in der **Manifest**-Dropdownliste auf die Option **Create Application Without a Manifest** (Anwendung ohne ein Manifest erstellen) klicken. Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Weitere Informationen zum Erstellen von Manifesten finden Sie unter [-win32manifest (C#-Compileroptionen)](./win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
