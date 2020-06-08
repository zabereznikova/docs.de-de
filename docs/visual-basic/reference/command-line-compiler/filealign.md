---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 3877757185030b0dba914a79d8c760fb8033ae5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408646"
---
# <a name="-filealign"></a>-filealign
Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Erforderlich. Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `-filealign`-Option verwenden, um die Ausrichtung der Abschnitte in Ihrer Ausgabedatei anzugeben. Abschnitte sind Blöcke zusammenhängenden Speichers in einer Portable Executable-Datei (PE), die entweder Code oder Daten enthält. Die `-filealign`-Option ermöglicht es Ihnen, Ihre Anwendung mit einer nicht dem Standardwert entsprechenden Ausrichtung zu kompilieren. Die meisten Entwickler müssen diese Option nicht verwenden.  
  
 Jeder Abschnitt wird an einer Grenze ausgerichtet, die einem Vielfachen des `-filealign`-Werts entspricht. Es gibt keinen festen Standardwert. Wenn `-filealign` nicht angegeben wird, wählt der Compiler zur Kompilierzeit einen Standardwert.  
  
 Durch Angeben der Abschnittsgröße können Sie die Größe der Ausgabedatei ändern. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
> [!NOTE]
> Diese Option `-filealign` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
