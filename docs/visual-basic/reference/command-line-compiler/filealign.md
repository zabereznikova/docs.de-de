---
title: / filealign | Microsoft-Dokumentation
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
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 18d5c3e327e2e41f4786eda6c3e981125f87389d
ms.lasthandoff: 03/13/2017

---
# <a name="filealign"></a>/filealign
Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Erforderlich. Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte werden in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `/filealign` Option, um die Ausrichtung der Abschnitte in der Ausgabedatei anzugeben. Abschnitte sind zusammenhängende Arbeitsspeicherblöcke in einer PE (Portable Executable)-Datei, die entweder Code oder Daten enthält. Die `/filealign` -Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren, die meisten Entwickler müssen nicht auf diese Option verwenden.  
  
 Jeder Abschnitt wird an einer Grenze, die ein Vielfaches von ausgerichtet der `/filealign` Wert. Es gibt keinen festen Standardwert. Wenn `/filealign` nicht angegeben wird, wählt der Compiler einen Standardwert zum Zeitpunkt der Kompilierung.  
  
 Durch Angeben der, können Sie die Größe der Ausgabedatei ändern. Ändern der Größe für Programme möglicherweise hilfreich, die auf kleineren Geräten ausgeführt werden.  
  
> [!NOTE]
>  Die `/filealign` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
