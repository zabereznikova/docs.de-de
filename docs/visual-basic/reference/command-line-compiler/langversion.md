---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 72a5638a5c5364381ffd68604b0d44830d53f365
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344213"
---
# <a name="-langversion-visual-basic"></a>-Langversion (Visual Basic)
Bewirkt, dass der Compiler nur die Syntax akzeptiert, die in der angegebenen Visual Basic Sprachversion enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumente  
 `version`  
 Erforderlich Die Sprachversion, die während der Kompilierung verwendet werden soll. Akzeptierte Werte sind `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` und `latest`.

 Alle ganzzahligen Zahlen können auch mit `.0` als neben Version angegeben werden, z. b. `11.0`.

 Sie können die Liste aller möglichen Werte anzeigen, indem Sie `-langversion:?` in der Befehlszeile angeben.  
  
## <a name="remarks"></a>Hinweise  
 Die Option `-langversion` gibt an, welche Syntax der Compiler annimmt. Wenn Sie z. b. angeben, dass die Sprachversion 9,0 ist, generiert der Compiler Fehler für die Syntax, die nur in Version 10,0 und höher gültig ist.  
  
 Sie können diese Option verwenden, wenn Sie Anwendungen entwickeln, die auf unterschiedliche Versionen der .NET Framework abzielen. Wenn Sie z. b. .NET Framework 3,5 verwenden, können Sie diese Option verwenden, um sicherzustellen, dass Sie keine Syntax aus Sprachversion 10,0 verwenden.  
  
 Sie können `-langversion` nur über die Befehlszeile direkt festlegen. Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/visual-studio-multi-targeting-overview).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `sample.vb` für Visual Basic 9,0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/visual-studio-multi-targeting-overview)
