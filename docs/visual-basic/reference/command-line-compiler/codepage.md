---
title: -Codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002361"
---
# <a name="-codepage-visual-basic"></a>-Codepage (Visual Basic)
Gibt für alle Quellcodedateien in der Kompilierung die zu verwendende Codepage an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`id`|Erforderlich. Der Compiler verwendet die durch `id` angegebene Codepage, um die Codierung der Quelldateien zu interpretieren.|  
  
## <a name="remarks"></a>Hinweise  
 Zum Kompilieren von Quellcode, der mit einer bestimmten Codierung gespeichert wird, können Sie mit `-codepage` angeben, welche Codepage verwendet werden soll. Die Option "`-codepage`" gilt für alle Quell Code Dateien in der Kompilierung. Weitere Informationen finden Sie unter [Zeichencodierung in der .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 Die Option "`-codepage`" ist nicht erforderlich, wenn die Quell Code Dateien mit der aktuellen ANSI-Codepage, Unicode oder UTF-8 mit einer Signatur gespeichert wurden. Visual Studio speichert alle Quell Code Dateien standardmäßig mit der aktuellen ANSI-Codepage, es sei denn, der Benutzer gibt im **Codierungs** Dialogfeld eine andere Codierung an. Visual Studio verwendet das Dialogfeld **Codierung** , um Quell Code Dateien zu öffnen, die mit einer anderen Codepage gespeichert werden.  
  
> [!NOTE]
> Die Option "`-codepage`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
