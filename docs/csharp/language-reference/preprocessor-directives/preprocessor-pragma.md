---
description: '#pragma – C#-Referenz'
title: '#pragma – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 2788c2589bee149676c5cb2b4212ec7a060a47af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168516"
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
