---
title: /codepage (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 609373ed0e58eec86a703f33d48d31e27b0b7e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="codepage-visual-basic"></a>/codepage (Visual Basic)
Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`id`|Erforderlich. Der Compiler verwendet die Codepage, die vom angegebenen `id` zur Interpretation der Codierung der Quelldateien.|  
  
## <a name="remarks"></a>Hinweise  
 Um mit einer bestimmten Codierung gespeichert Quellcode zu kompilieren, können Sie `/codepage` angeben, welche Codepage verwendet werden soll. Die `/codepage` Option gilt für alle Quellcodedateien in der Kompilierung. Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 Die `/codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]alle Quellcodedateien standardmäßig mit der aktuellen ANSI-Codepage speichert, es sei denn, der Benutzer eine andere Codierung gibt die **Codierung** (Dialogfeld). [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode Dateien, die mit einer anderen Codepage gespeichert.  
  
> [!NOTE]
>  Die `/codepage` Option ist nicht verfügbar in der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Entwicklungsumgebung; ist verfügbar, nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
