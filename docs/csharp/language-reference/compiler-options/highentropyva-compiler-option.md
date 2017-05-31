---
title: -highentropyva (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /highentropyva
dev_langs:
- CSharp
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c1b49faa2fb388b330c24bdff28d00872828b110
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="highentropyva-c-compiler-options"></a>/highentropyva (C#-Compileroptionen)
Die **/highentropyva**-Compileroption informiert den Windows-Kernel, ob eine bestimmte ausführbare Datei ASLR mit hoher Entropie (Address Space Layout Randomization, Zufällige Anordnung des Layouts des Adressraums) unterstützt wird.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Diese Option gibt an, dass eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die durch die Compileroption [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) gekennzeichnet ist, einen virtuellen Adressbereich mit hoher Entropie unterstützt. Diese Option ist standardmäßig deaktiviert. Verwenden Sie **/highentropyva+** oder **/highentropyva**, um sie zu aktivieren.  
  
## <a name="remarks"></a>Hinweise  
 Die Option **/highentropyva** ermöglicht den kompatiblen Versionen des Windows-Kernels, ein höheres Maß an Entropie zu verwenden, wenn das Adressbereichlayout eines Prozesses als Teil von ASLR zufällig festgelegt wird. Die Verwendung eines höheren Maßes an Entropie bedeutet, dass viel mehr Adressen Speicherbereichen, z.B. Stapel und Heaps, zugeordnet werden können. Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.  
  
 Wenn die **/highentropyva**-Compileroption angegeben wird, müssen die ausführbare Zieldatei und alle Module, von denen sie abhängig ist, Zeigerwerte verarbeiten können, die größer als 4 Gigabytes (GB) sind, wenn sie als 64-Bit-Prozess ausgeführt werden.
