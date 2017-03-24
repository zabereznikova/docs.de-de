---
title: / highentropyva (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34987930b3afd6d95d12190172a5a5e512106f8a
ms.lasthandoff: 03/13/2017

---
# <a name="highentropyva-visual-basic"></a>/highentropyva (Visual Basic)
Gibt an, ob eine 64-Bit-ausführbare Datei oder eine ausführbare Datei, die von markiert ist die [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption Address Space Layout Randomization (ASLR) mit hohen Entropie unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Optional. Die Option ist standardmäßig deaktiviert, oder wenn Sie angeben, `/highentropyva-`. Die Option ist die Angabe `/highentropyva` oder `/highentropyva+`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Option angeben, können kompatible Versionen des Windows-Kernels höheres Maß an Entropie, wenn der Kernel das Layout für die Adressen Speicherplatz eines Prozesses als Teil von ASLR Einzelteilen. Wenn der Kernel höheres Maß an Entropie verwendet wird, kann eine größere Anzahl von Adressen Speicherbereiche, z. B. Stapel und Heaps zugeordnet werden. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die Option auf der ausführbaren Zieldatei und alle Module auf muss denen es abhängig ist, sein Zeigerwerte verarbeiten, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
