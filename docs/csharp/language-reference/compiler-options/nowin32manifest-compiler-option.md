---
description: -nowin32manifest (C#-Compileroptionen)
title: -nowin32manifest (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 13bbee66901149d54632d9b164431f8898cdf52e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193997"
---
# <a name="-nowin32manifest-c-compiler-options"></a>-nowin32manifest (C#-Compileroptionen)

Verwenden Sie die Option **-nowin32manifest**, um den Compiler anzuweisen, kein Anwendungsmanifest in die ausführbare Datei einzubetten.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a>Hinweise  

 Wenn diese Option verwendet wird, unterliegt die Anwendung der Virtualisierung unter Windows Vista, es sei denn, Sie stellen ein Anwendungsmanifest in einer Win32-Ressourcendatei oder einem späteren Buildschritt bereit.  
  
 Legen Sie diese Option in Visual Studio auf der Seite **Application Property** (Anwendungseigenschaft) fest, indem Sie in der **Manifest**-Dropdownliste auf die Option **Create Application Without a Manifest** (Anwendung ohne ein Manifest erstellen) klicken. Weitere Informationen finden Sie unter [Seite „Anwendung“, Projekt-Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Weitere Informationen zum Erstellen von Manifesten finden Sie unter [-win32manifest (C#-Compileroptionen)](./win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
