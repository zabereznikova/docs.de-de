---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 383b6adae94c27efdd236de31ddfa8d16a6d4648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-codepage-visual-basic"></a>-Codepage (Visual Basic)
Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`id`|Erforderlich. Der Compiler verwendet die Codepage, die vom angegebenen `id` zur Interpretation der Codierung der Quelldateien.|  
  
## <a name="remarks"></a>Hinweise  
 Um mit einer bestimmten Codierung gespeichert Quellcode zu kompilieren, können Sie `-codepage` angeben, welche Codepage verwendet werden soll. Die `-codepage` Option gilt für alle Quellcodedateien in der Kompilierung. Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 Die `-codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden. Visual Studio speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage standardmäßig, es sei denn, der Benutzer gibt an, einer anderen Codierung der **Codierung** (Dialogfeld). Visual Studio verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode Dateien, die mit einer anderen Codepage gespeichert.  
  
> [!NOTE]
>  Die `-codepage` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
