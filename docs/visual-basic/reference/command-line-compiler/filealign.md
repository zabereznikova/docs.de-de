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
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005596"
---
# <a name="-filealign"></a>-filealign
Gibt die Ausrichtung der Abschnitte der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>Argumente  
 `number`  
 Erforderlich. Ein-Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt. Gültige Werte sind 512, 1024, 2048, 4096 und 8192. Diese Werte sind in Bytes angegeben.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Option "`-filealign`" verwenden, um die Ausrichtung von Abschnitten in der Ausgabedatei anzugeben. Abschnitte sind Blöcke des zusammenhängenden Speichers in einer portablen ausführbaren Datei (PE), die entweder Code oder Daten enthält. Mit der Option "`-filealign`" können Sie die Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren. die meisten Entwickler müssen diese Option nicht verwenden.  
  
 Jeder Abschnitt wird an einer Grenze ausgerichtet, die ein Vielfaches des `-filealign`-Werts ist. Es gibt keinen festen Standardwert. Wenn `-filealign` nicht angegeben ist, wählt der Compiler zum Zeitpunkt der Kompilierung einen Standardwert aus.  
  
 Durch Angeben der Abschnitts Größe können Sie die Größe der Ausgabedatei ändern. Das Ändern der Größe kann möglicherweise für Programme hilfreich sein, die auf kleineren Geräten ausgeführt werden.  
  
> [!NOTE]
> Die Option "`-filealign`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
