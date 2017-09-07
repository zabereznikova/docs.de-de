---
title: -codepage (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a>/codepage (C#-Compileroptionen)
Diese Option gibt an, welche Codepage beim Kompilieren verwendet werden soll, wenn die erforderliche Seite nicht die aktuelle Standardcodepage für das System ist.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
 `id`  
 Die ID der Codepage, die für alle Quellcodedateien in der Kompilierung verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine oder mehrere Quellcodedateien kompilieren, für die beim Erstellen nicht die Verwendung der Standardcodepage auf dem Computer festgelegt wurde, können Sie die Option **/codepage** verwenden, um anzugeben, welche Codeseite verwendet werden soll. **/codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.  
  
 Wenn die Quellcodedateien mit der auf dem Computer aktivierten Codepage oder mit UNICODE bzw. UTF-8 erstellt wurden, müssen Sie **/codepage** nicht verwenden.  
  
 Weitere Informationen darüber, wie ermittelt wird, welche Codeseiten auf dem System unterstützt werden, finden Sie unter [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371).  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

