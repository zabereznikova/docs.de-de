---
title: -codepage (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 66edb32d24dd1dc543097b98ff3744f0aa0a7145
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511871"
---
# <a name="-codepage-c-compiler-options"></a>-codepage (C#-Compileroptionen)
Diese Option gibt an, welche Codepage beim Kompilieren verwendet werden soll, wenn die erforderliche Seite nicht die aktuelle Standardcodepage für das System ist.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
 `id`  
 Die ID der Codepage, die für alle Quellcodedateien in der Kompilierung verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine oder mehrere Quellcodedateien kompilieren, für die beim Erstellen nicht die Verwendung der Standardcodepage auf dem Computer festgelegt wurde, können Sie die Option **-codepage** verwenden, um anzugeben, welche Codepage verwendet werden soll. **-codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.  
  
 Wenn die Quellcodedateien mit der auf dem Computer aktivierten Codepage oder mit UNICODE bzw. UTF-8 erstellt wurden, müssen Sie **-codepage** nicht verwenden.  
  
 Weitere Informationen darüber, wie ermittelt wird, welche Codeseiten auf dem System unterstützt werden, finden Sie unter [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
