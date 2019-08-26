---
title: '#pragma – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65ca38ff6993117b6ed9f716d4ac93ba2d4a9ddf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605665"
---
# <a name="pragma-c-reference"></a>#pragma (C#-Referenz)
`#pragma` gibt dem Compiler spezielle Anweisungen für die Kompilierung der Datei, in der es auftritt. Die Anweisungen müssen vom Compiler unterstützt werden. Das heißt, Sie können `#pragma` nicht zum Erstellen von benutzerdefinierten Vorverarbeitungsanweisungen verwenden. Der Microsoft C#-Compiler unterstützt die folgenden beiden `#pragma`-Anweisungen:  
  
 [#pragma warning](./preprocessor-pragma-warning.md)  
  
 [#pragma checksum](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Syntax  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Parameter  
 `pragma-name`  
 Der Name einer erkannten pragma-Anweisung.  
  
 `pragma-arguments`  
 Pragma-spezifische Argumente.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
- [#pragma warning](./preprocessor-pragma-warning.md)
- [#pragma checksum](./preprocessor-pragma-checksum.md)
