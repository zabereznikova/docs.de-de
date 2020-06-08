---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 405b557568a736de3ddc3b51e265261222613131
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403030"
---
# <a name="-verbose"></a>-verbose
Bewirkt, dass der Compiler ausführliche Status- und Fehlermeldungen erzeugt  
  
## <a name="syntax"></a>Syntax  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Wenn Sie `-verbose` angeben, ist der Effekt mit `-verbose+` identisch: Der Compiler gibt ausführliche Meldungen aus. Der Standardwert für diese Option ist `-verbose-`.  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-verbose` zeigt Informationen zur Gesamtanzahl der Fehler an, die vom Compiler ausgegeben werden, sowie welche Dateien derzeit kompiliert werden und meldet, welche Assemblys von einem Modul geladen werden.  
  
> [!NOTE]
> Die Option `-verbose` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `In.vb` und weist den Compiler an, ausführliche Statusinformationen anzuzeigen.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
