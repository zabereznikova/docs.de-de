---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.custom: updateeachrelease
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 9921df0b8bb1a4808528b58a5a38d75e5e3fbdd2
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359258"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)

Führt dazu, dass der Compiler nur Syntax akzeptiert, die in der ausgewählten Visual Basic-Sprachversion enthalten ist  
  
## <a name="syntax"></a>Syntax  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumente

 `version`\
 Erforderlich. Die Sprachversion, die während der Kompilierung verwendet werden soll. Folgende Werte werden akzeptiert: `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `16`, `default` und `latest`.

 Alle ganzzahligen Zahlen können auch mit `.0` als Nebenversion angegeben werden, z. B. `11.0`.

 Sie können die Liste aller möglichen Werte anzeigen, indem Sie `-langversion:?` in der Befehlszeile angeben.

## <a name="remarks"></a>Hinweise

Die Option `-langversion` gibt an, welche Syntax der Compiler akzeptiert. Wenn Sie z. B. angeben, dass die Sprachversion 9.0 ist, generiert der Compiler Fehler für Syntax, die nur in Version 10.0 und höher gültig ist.

Sie können diese Option verwenden, wenn Sie Anwendungen für unterschiedliche Versionen des .NET Framework entwickeln. Wenn Sie z. B. .NET Framework 3.5 verwenden, können Sie mithilfe dieser Option sicherstellen, dass Sie keine Syntax aus Sprachversion 10.0 verwenden.

Sie können `-langversion` nur über die Befehlszeile direkt festlegen. Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET-Framework-Zielversion](/visualstudio/ide/visual-studio-multi-targeting-overview).

## <a name="example"></a>Beispiel

Der folgende Code kompiliert `sample.vb` für Visual Basic 9.0.

```console
vbc -langversion:9.0 sample.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
