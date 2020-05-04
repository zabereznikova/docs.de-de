---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 7934dcaada4675bf687624bef5ed1ea25e842832
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344240"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
Gibt an, ob eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) gekennzeichnet ist, die zufällige Anordnung des Adressraumlayouts (Address Space Layout Randomization, ASLR) mit hoher Entropie unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Standardmäßig oder bei Angabe von `-highentropyva-` ist diese Option nicht aktiviert. Bei Angabe von `-highentropyva` oder `-highentropyva+` ist die Option aktiviert.  
  
## <a name="remarks"></a>Hinweise  
 Durch Angabe dieser Option können kompatible Versionen des Windows-Kernels ein höheres Maß an Entropie verwenden, wenn der Kernel das Adressraumlayout eines Prozesses als Teil von ASLR zufällig festlegt. Wenn der Kernel ein höheres Maß an Entropie verwendet, können weit mehr Adressen Speicherbereichen, wie etwa Stapel und Heaps, zugeordnet werden. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Ist die Option aktiviert, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 GB sind, wenn die Module als 64-Bit-Prozess ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
