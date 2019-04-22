---
title: -Highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 16bfea37a5742ac5aaaabfacdcf03a2b5bedb6db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819278"
---
# <a name="-highentropyva-visual-basic"></a>-Highentropyva (Visual Basic)
Gibt an, ob eine 64-Bit ausführbare Datei oder eine ausführbare Datei, die gekennzeichnet ist, indem die [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption von Address Space Layout Randomization (ASLR) mit hoher Entropie unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Die Option ist standardmäßig deaktiviert, oder bei Angabe von `-highentropyva-`. Die Option ist auf, wenn Sie angeben, `-highentropyva` oder `-highentropyva+`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option angeben, können kompatible Versionen des Windows-Kernels höheres Maß an Entropie, wenn der Kernel das Adresse Speicherplatz Layout eines Prozesses als Teil von ASLR Einzelteilen. Wenn der Kernel höheres Maß an Entropie verwendet wird, kann eine größere Anzahl von Adressen Speicherbereichen, z.B. Stapel und Heaps zugeordnet werden. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die Option für die ausführbare Zieldatei und alle Module auf muss dem es abhängig ist, Zeigerwerte verarbeiten, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden können.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
