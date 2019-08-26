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
ms.openlocfilehash: c85cd8935bcefd1353707624052b62ee982f7b07
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69603050"
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
  
## <a name="remarks"></a>Anmerkungen  
 Der Compiler versucht zunächst, alle Quelldateien als UTF-8 zu interpretieren. Wenn Ihre Quellcodedateien eine andere Codierung als UTF-8 aufweisen und andere Zeichen als 7-Bit-ASCII-Zeichen verwendet werden, sollten Sie mit der Option **-codepage** angeben, welche Codeseite verwendet werden soll. **-codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.  
    
 Weitere Informationen darüber, wie ermittelt wird, welche Codeseiten auf dem System unterstützt werden, finden Sie unter [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo).  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
