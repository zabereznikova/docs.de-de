---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004974"
---
# <a name="-verbose"></a>-verbose
Bewirkt, dass der Compiler ausführliche Status-und Fehlermeldungen erzeugt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Das Angeben von `-verbose` ist identisch mit dem Angeben von `-verbose+`, was bewirkt, dass der Compiler ausführliche Meldungen ausgibt. Der Standardwert für diese Option ist `-verbose-`.  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-verbose` zeigt Informationen zur Gesamtanzahl von Fehlern an, die vom Compiler ausgegeben werden, meldet, welche Assemblys von einem Modul geladen werden, und zeigt an, welche Dateien derzeit kompiliert werden.  
  
> [!NOTE]
> Die Option "`-verbose`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `In.vb` und weist den Compiler an, ausführliche Statusinformationen anzuzeigen.  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
