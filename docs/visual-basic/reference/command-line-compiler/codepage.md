---
title: / Codepage (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
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
ms.openlocfilehash: 90dce6e34e52862807e2acdbf1850699316730d1
ms.lasthandoff: 03/13/2017

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
|`id`|Erforderlich. Der Compiler verwendet die durch angegebene Codepage `id` zur Interpretation der Codierung der Quelldateien.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Kompilieren von Quellcode mit einer bestimmten Codierung gespeichert, können Sie `/codepage` angeben, welche Codepage verwendet werden soll. Die `/codepage` -Option gilt für alle Quellcodedateien in der Kompilierung. Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).  
  
 Die `/codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 und einer Signatur gespeichert wurden. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]Speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage standardmäßig, angegeben werden, wenn der Benutzer eine andere Codierung der **Codierung** Dialogfeld. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode-Dateien, die mit einer anderen Codepage gespeichert.  
  
> [!NOTE]
>  Die `/codepage` Option ist nicht verfügbar der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Entwicklungsumgebung; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
