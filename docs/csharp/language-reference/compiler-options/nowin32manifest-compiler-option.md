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
ms.openlocfilehash: 3ab52d541c169850f6ae7ba7e7cfded290f890e7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530508"
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
  
 Weitere Informationen zum Erstellen von Manifesten finden Sie unter [-win32manifest (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
