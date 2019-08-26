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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602559"
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
  
## <a name="remarks"></a>Anmerkungen  
 Sie können die Compileroption `-preferreduilang` verwenden, um die Sprache anzugeben, die der C#-Compiler für Fehlermeldungen und andere Befehlszeilenausgaben verwenden soll. Wenn das Sprachpaket für die Sprache nicht installiert ist, wird stattdessen die Spracheinstellung des Betriebssystems verwendet und kein Fehler gemeldet.  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
