---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 7934dcaada4675bf687624bef5ed1ea25e842832
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344240"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Gibt an, ob eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die von der [-Plattform: anycpu-](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption gekennzeichnet ist, eine hohe Entropie Address Space Layout Randomization (ASLR) unter  
  
## <a name="syntax"></a>Syntax  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Die Option ist standardmäßig deaktiviert, oder wenn Sie `-highentropyva-`angeben. Wenn Sie `-highentropyva` oder `-highentropyva+`angeben, ist die Option auf ON festgelegt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option angeben, können kompatible Versionen des Windows-Kernels ein höheres Maß an Entropie verwenden, wenn der Kernel das Adressraum Layout eines Prozesses als Teil von ASLR anordnet. Wenn der Kernel ein höheres Maß an Entropie verwendet, kann den Arbeitsspeicher Bereichen wie Stapeln und Heaps eine größere Anzahl von Adressen zugewiesen werden. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die Option auf ON festgelegt ist, müssen die ausführbare Zieldatei und alle Module, von denen Sie abhängig ist, Zeiger Werte verarbeiten können, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
