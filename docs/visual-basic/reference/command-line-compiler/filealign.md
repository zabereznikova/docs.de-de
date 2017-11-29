---
title: /filealign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dbabc19c85501b97ef5443a6f6e12524f8de7d91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="filealign"></a>/filealign
Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Erforderlich. Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `/filealign` Option, um die Ausrichtung der Abschnitte in der Ausgabedatei anzugeben. Abschnitte sind Blöcke zusammenhängender Arbeitsspeicher in einer PE (Portable Executable)-Datei, die entweder Code oder Daten enthält. Die `/filealign` Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren, d. h. die meisten Entwickler müssen nicht auf diese Option verwenden.  
  
 Jeder Abschnitt ist an einer Grenze, die ein Vielfaches von ausgerichtet der `/filealign` Wert. Es gibt keinen festen Standardwert. Wenn `/filealign` nicht angegeben wird, wählt der Compiler einen Standardwert zum Zeitpunkt der Kompilierung.  
  
 Indem Sie den Abschnittsgröße angeben, können Sie die Größe der Ausgabedatei ändern. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
> [!NOTE]
>  Die `/filealign` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
