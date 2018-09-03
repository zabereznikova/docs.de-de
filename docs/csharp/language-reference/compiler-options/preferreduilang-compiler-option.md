---
title: -preferreduilang (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: a1fbbb8415e5e3405f039489aa071b0624065a9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405890"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang (C#-Compileroptionen)
Mithilfe der Compileroption `-preferreduilang` können Sie die Sprache festlegen, in der der C#-Compiler Ausgaben anzeigt, wie z.B. Fehlermeldungen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>Argumente  
 `language`  
 Der [language name](/windows/desktop/Intl/language-names) (Sprachenname) der Sprache, die für die Compilerausgabe verwendet wird.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll. Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
