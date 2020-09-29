---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 4d88c302281097fabd0eb361d60319bc8a0daf8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058065"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)

Gibt an, ob eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](platform.md) gekennzeichnet ist, die zufällige Anordnung des Adressraumlayouts (Address Space Layout Randomization, ASLR) mit hoher Entropie unterstützt.  
  
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

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
