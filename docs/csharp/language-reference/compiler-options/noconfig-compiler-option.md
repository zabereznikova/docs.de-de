---
title: -noconfig (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: b689a4bf0d8a1e57bf36f8ded7f2c9308f241670
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402693"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (C#-Compileroptionen)
Die Option **-noconfig** weist den Compiler dazu an, nicht mit der Datei „csc.rsp“ zu kompilieren, die sich im gleichen Verzeichnis wie die Datei „csc.exe“ befindet und daraus geladen wird.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Datei „csc.rsp“ verweist auf alle Assemblys, die im Lieferumfang von .NET Framework enthalten sind. Die tatsächlichen Verweise, die die .NET-Entwicklungsumgebung von Visual Studio enthält, hängen vom Projekttyp ab.  
  
 Sie können die Datei „csc.rsp“ ändern und zusätzliche Compileroptionen angeben, die in jeder Kompilierung über die Befehlszeile mit „csc.exe“ enthalten sein sollen (mit Ausnahme der Option **-noconfig**).  
  
 Der Compiler verarbeitet die an den Befehl **csc** übergebenen Optionen zuletzt. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei „csc.rsp“.  
  
 Wenn der Compiler nach den Einstellungen in der Datei „csc.rsp“ suchen und diese verwenden soll, geben Sie **-noconfig** an.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
