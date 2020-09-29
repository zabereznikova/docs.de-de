---
description: -highentropyva (C#-Compileroptionen)
title: -highentropyva (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: f3cdeb5e63d632fecbbd94501558cc53c28a918a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173203"
---
# <a name="-highentropyva-c-compiler-options"></a>-highentropyva (C#-Compileroptionen)

Die Compileroption **-highentropyva** informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt wird.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  

 `+` &#124; `-`  
 Diese Option gibt an, dass eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [-platform:anycpu](./platform-compiler-option.md) gekennzeichnet ist, einen virtuellen Adressbereich mit hoher Entropie unterstützt. Diese Option ist standardmäßig deaktiviert. Verwenden Sie **-highentropyva+** oder **-highentropyva**, um sie zu aktivieren.  
  
## <a name="remarks"></a>Bemerkungen  

 Die Option **-highentropyva** ermöglicht den kompatiblen Versionen des Windows-Kernels, ein höheres Maß an Entropie zu verwenden, wenn das Adressbereichlayout eines Prozesses als Teil von ASLR zufällig festgelegt wird. Die Verwendung eines höheren Maßes an Entropie bedeutet, dass viel mehr Adressen Speicherbereichen, z.B. Stapel und Heaps, zugeordnet werden können. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die Compileroption **-highentropyva** angegeben wird, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 Gigabyte (GB) sind, wenn sie als 64-Bit-Prozess ausgeführt werden.
