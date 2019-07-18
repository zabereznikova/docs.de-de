---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944702"
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
|`id`|Erforderlich. Der Compiler verwendet die Codepage, die anhand des `id` interpretiert die Codierung der Quelldateien.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Kompilieren von Quellcode mit einer bestimmten Codierung gespeichert, können Sie `-codepage` angeben, welche Codeseite verwendet werden soll. Die `-codepage` Option gilt für alle Quellcodedateien in der Kompilierung. Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Die `-codepage` Option ist nicht erforderlich, wenn die Quellcodedateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden. Visual Studio speichert alle Quellcodedateien mit der aktuellen ANSI-Codepage in der Standardeinstellung, wenn der Benutzer gibt eine andere Codierung der **Codierung** Dialogfeld. Visual Studio verwendet die **Codierung** Dialogfeld zum Öffnen von Quellcode-Dateien, die mit einer anderen Codepage gespeichert.  
  
> [!NOTE]
>  Die `-codepage` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
